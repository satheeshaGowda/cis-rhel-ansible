Ansible + CIS Benchmarks + RHEL/CentOS 6
====

This is an ansible playbook for automatically applying CIS Security Benchmarks to a system running Red Hat Enterprise Linux 6 or CentOS 6.

What are these benchmarks?
--

The [Center for Internet Security](http://www.cisecurity.org/) publishes [security benchmarks](http://benchmarks.cisecurity.org/) for various systems.

***Please be aware that I'm not affiliated with CIS in any way and the data in this repository has absolutely no relation to CIS.***

What does this playbook do?
--

The playbook will attempt to configure your system to meet as many of the CIS security benchmarks as possible.  Any benchmarks marked as "not scored" or benchmarks that are only checks will be skipped.

How do I run it?
--

**Don't run this blindly on an actively running system.**  The playbook will make ***serious*** modifications to your system that could affect its availability.

Perform a dry run first:

    ansible-playbook -i hosts -C playbook.yaml

To apply the changes simply run:

    ansible-playbook -i hosts playbook.yaml

Tags are available for running a section at a time:

    # Test only items from section 4
    ansible-playbook -i hosts -C playbook.yml -t section4
    
    # Apply changes only from items in section 4
    ansible-playbook -i hosts playbook.yml -t section4

You can combine tags to run items from multiple sections:

    ansible-playbook -i hosts playbook.yml -t "section4,section7"

Something doesn't work. You're awful at ansible playbooks.
--

Patches and pull requests are welcomed! :)
