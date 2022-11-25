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
4. Under `roles/template-example/templates` create file called `hello.txt.j2` with following content:
```
Hello, this is dynamic template
Your variable value is: {hello}
```
5. Under `roles/template-example/tasks` create file called `main.yml`
6. In `roles/template-example/tasks/main.yml` we need only 1 task so let's add it
```
- name: Template a file to /tmp/hello2.txt
  <define here template module>
```
7. Implement rest by checking the following link: https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html