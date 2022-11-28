# Tags!

In this exercise we will try out tags to run different tasks based on given tasks

## Goal
Let's create playbook that will create us 2 different files based on the tags provided

## Steps

1. Examine the following files:
  * `tags/roles/files/serious_file1.txt`
  * `tags/roles/files/serious_file2.txt`
  * `tags/roles/tasks/main.yml`

2. Add the following tags to `tags/roles/tasks/main.yml`
  * file1
    * this goes to task where file1 is created
  * file2
    * this goes to task where file2 is created
  * Check how to add tags from here: https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_tags.html

3. Now run command `ansible-playbook playbook.yml --tags "file1"
4. Check the tmp file with `ls -al /tmp` and `cat /tmp/serious_file1.txt`. What is the outcome?
5. Now run the command with `--tags "file2"` instead of `file1`. What is the outcome this time?