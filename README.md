A ready-to-use Ansible playbook for the [Galaxy Tools role][gtr].

Before you can use this playbook, you need to install [Ansible][ans]:

    $ pip install ansible

To use, clone this repo and edit `tools.yml` file to provide your API key and
a URL to the Galaxy instance (if different from your local machine).
Then, provide the list of tools to install in the file `files/tool_list.yaml`.
Once that's set, run the playbook with

    $ ansible-playbook tools.yml -i "localhost,"

In addition to the output from running the playbook, the installation script
will log it's progress in `/tmp/galaxy_tool_install.log`.

[gtr]: https://github.com/galaxyproject/ansible-galaxy-tools
[ans]: http://www.ansible.com/home
