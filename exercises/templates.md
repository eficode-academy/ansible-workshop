# Templates!

In this exercise we will create role to create dynamic local file under `/tmp/` folder with using templates.

## Goal
Let's create ansible playbook that can create us local files under `/tmp` based on given variable values

## Steps

1. Create folder `roles` under `templates`
2. Under `roles` let's create `template-example`
3. Under `template-example` let's create following folders:
  * `tasks`
  * `templates`
4. Under `roles/templates-example/templates` create file called `hello.txt.j2` with following content:
```
Hello, this is dynamic template
Your variable value is: {{hello}}
```
5. Under `roles/templates-example/tasks` create file called `main.yml`
6. In `roles/templates-example/tasks/main.yml` we need only 1 task so let's add it
```
- name: Template a file to /tmp/hello2.txt
  <define here template module>
  vars:
    hello: <variable_value>
```
7. Implement rest by checking the following link: https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html

8. Now that we've created a role we need to bind it to our playbook. Create new file under `templates` called `playbook.yml`
```
---
  - hosts: 127.0.0.1
    connection: local
    roles:
      - templates-example
```

9. Run the playbook with `ansible-playbook playbook.yml`

10. Verify the results are correct by running `cat /tmp/hello2.txt`, output should be
```
$ cat /tmp/hello2.txt
Hello, this is dynamic template
Your variable value is: <variable_value_that_was_defined>
```