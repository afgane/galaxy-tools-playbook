A ready-to-use Ansible playbook for the [Galaxy Tools role][gtr].

Before you can use this playbook, you need to install [Ansible][ans] (version
2.1.2.0+ is required). Note that for the time being, this playbook does not
work with Python 3.x.

    $ pip install ansible virtualenv

To use, clone this repo and provide a list of tools to install. A sample file
if provided in `files/sample_tool_list.yaml`. , run the playbook:

    $ git clone https://github.com/afgane/galaxy-tools-playbook.git
    $ cd galaxy-tools-playbook && ansible-galaxy install -f -r requirements_roles.yml -p roles
    # Provide a list of tools in files/sample_tool_list.yaml
    # Edit tools.yml if you're not targeting Galaxy on localhost:8080
    $ ansible-playbook tools.yml -i "localhost," --extra-vars galaxy_tools_api_key=<Admin user API key>

In addition to the output from running the playbook, the installation script
will log it's progress in `/tmp/galaxy_tool_install.log`.

The default settings will run the playbook for an installation of Galaxy on
your local machine. To target a different instance of Galaxy, edit `tools.yml`
and set a URL to the Galaxy instance. You can also set the API key there not
to have to provide it on the command line.

Updates
-------
To update the version of the galaxy-tools role, run the following command
`ansible-galaxy install -f -r requirements_roles.yml -p roles`

[gtr]: https://github.com/galaxyproject/ansible-galaxy-tools
[ans]: http://www.ansible.com/home
