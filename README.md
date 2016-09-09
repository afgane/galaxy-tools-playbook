A ready-to-use Ansible playbook for the [Galaxy Tools role][gtr].

Before you can use this playbook, you need to install [Ansible][ans]:

    $ pip install ansible

To use, clone this repo and provide a list of tools to install via
`files/tool_list.yaml` file. Then, run the playbook:

    $ git clone https://github.com/afgane/galaxy-tools-playbook.git
    $ ansible-galaxy install -f -r requirements_roles.yml -p roles
    # Provide a list of tools in files/tool_list.yaml
    $ ansible-playbook tools.yml -i "localhost," --extra-vars galaxy_tools_api_key=<Admin user API key>

In addition to the output from running the playbook, the installation script
will log it's progress in `/tmp/galaxy_tool_install.log`.

The default settings will run the playbook for an installation of Galaxy on
your local machine. To target a different instance of Galaxy, edit `tools.yml`
and set a URL to the Galaxy instance. You can also set the API key there not
to have to provide it on the command line.

[gtr]: https://github.com/galaxyproject/ansible-galaxy-tools
[ans]: http://www.ansible.com/home
