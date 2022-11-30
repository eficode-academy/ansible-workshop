# Hello world!

In this exercise we will create role to create hard-coded local file under `/tmp/` folder.

## Goal
Let's create hello world example playbook with ansible against localhost

## Steps

1. Create folder `roles`
2. Under `roles` let's create `hello-world`
3. Under `hello-world` let's create following folders:
  * `tasks`
  * `files`
4. Under `roles/hello-world/files` create file called `hello.txt`
  * Write there `Hello world!`
5. Under `roles/hello-world/tasks` create file called `main.yml`
6. In `roles/hello-world/tasks/main.yml` we need only 1 task so let's add it
 ```
 - name: Set hello.txt in place
  <define here copy module>
```` 
7. Implement rest by checking the following link: https://docs.ansible.com/ansible/2.9/modules/copy_module.html
  * dest should be `/tmp/hello.txt`
  * src should be `hello.txt`
  * owner can be checked with `whoami` command
  * group can be checked with `groups` command

8. Now that we've created a role we need to bind it to our playbook. Create new file under `hello-world` called `playbook.yml`
```
---
  - hosts: 127.0.0.1
    connection: local
    roles:
      - hello-world
```

9. Run the playbook with `ansible-playbook playbook.yml`

10. Verify the results are correct by running `cat /tmp/hello.txt`, output should be
```
$cat /tmp/hello.txt
Hello world!
```

