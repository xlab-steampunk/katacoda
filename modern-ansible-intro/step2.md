Let us start with something relatively simple save the following content into
the `play.yaml` file:

<pre class="file" data-filename="play.yaml" data-target="replace">
---
- name: Configure local computer
  hosts: localhost

  tasks:
    - name: Create config file
      ansible.builtin.copy:
        dest: /tmp/my.cfg
        content: Hello, World!
</pre>


Even if you never heard about Ansible playbook or YAML before, you probably
guessed that we want to create the `/tmp/my.cfg` file with the `Hello, World!`
inside it on our local computer. Let us test this by running the following
command:

`ansible-playbook play.yaml`{{execute}}

And sure enough, if we run the `cat /tmp/my-cfg.txt`{{execute}} command, the
hello is there ;) But how did Ansible know what to do? Explanation time ;)
