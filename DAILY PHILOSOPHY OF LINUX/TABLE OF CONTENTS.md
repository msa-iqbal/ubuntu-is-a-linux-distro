```plaintext
ubuntu-is-a-linux-distro/
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── ROADMAP.md
├── CHANGELOG.md
│
├── fundamentals/
│   ├── what-is-linux.md
│   ├── linux-architecture.md
│   ├── distributions.md
│   ├── ubuntu-overview.md
│   ├── kernel-vs-userspace.md
│   ├── filesystem-hierarchy-standard.md
│   ├── users-and-groups.md
│   ├── permissions.md
│   ├── environment-variables.md
│   └── boot-process.md
│
├── terminal/
│   ├── terminal-basics.md
│   ├── bash.md
│   ├── zsh.md
│   ├── shell-expansion.md
│   ├── aliases.md
│   ├── redirection.md
│   ├── pipes.md
│   ├── command-substitution.md
│   ├── xargs.md
│   └── tmux.md
│
├── package-management/
│   ├── apt.md
│   ├── apt-get.md
│   ├── apt-cache.md
│   ├── dpkg.md
│   ├── repositories.md
│   ├── ppa.md
│   ├── snap.md
│   ├── flatpak.md
│   ├── package-signatures.md
│   └── troubleshooting.md
│
├── files-and-directories/
│   ├── pwd.md
│   ├── ls.md
│   ├── cd.md
│   ├── cp.md
│   ├── mv.md
│   ├── rm.md
│   ├── mkdir.md
│   ├── touch.md
│   ├── tree.md
│   ├── find.md
│   ├── locate.md
│   ├── file.md
│   ├── stat.md
│   └── symbolic-links.md
│
├── text-processing/
│   ├── cat.md
│   ├── less.md
│   ├── head.md
│   ├── tail.md
│   ├── grep.md
│   ├── sed.md
│   ├── awk.md
│   ├── cut.md
│   ├── tr.md
│   ├── sort.md
│   ├── uniq.md
│   ├── wc.md
│   └── jq.md
│
├── process-management/
│   ├── ps.md
│   ├── top.md
│   ├── htop.md
│   ├── kill.md
│   ├── pkill.md
│   ├── nice.md
│   ├── jobs.md
│   ├── fg-bg.md
│   ├── nohup.md
│   └── system-monitoring.md
│
├── networking/
│   ├── networking-basics.md
│   ├── ip.md
│   ├── ifconfig.md
│   ├── ping.md
│   ├── traceroute.md
│   ├── netstat.md
│   ├── ss.md
│   ├── nslookup.md
│   ├── dig.md
│   ├── curl.md
│   ├── wget.md
│   ├── ftp.md
│   ├── dns.md
│   ├── tcp-ip.md
│   ├── ports.md
│   └── subnetting.md
│
├── ssh/
│   ├── ssh-basics.md
│   ├── ssh-config.md
│   ├── ssh-keys.md
│   ├── scp.md
│   ├── rsync.md
│   ├── ssh-tunneling.md
│   └── ssh-security.md
│
├── system-administration/
│   ├── sudo.md
│   ├── hostname.md
│   ├── users.md
│   ├── groups.md
│   ├── systemd.md
│   ├── services.md
│   ├── journalctl.md
│   ├── cron.md
│   ├── timers.md
│   ├── logs.md
│   ├── backups.md
│   ├── mounting.md
│   ├── swap.md
│   └── timezone.md
│
├── storage/
│   ├── disks.md
│   ├── partitions.md
│   ├── fdisk.md
│   ├── lsblk.md
│   ├── mount.md
│   ├── fstab.md
│   ├── filesystem-types.md
│   ├── lvm.md
│   └── raid.md
│
├── security/
│   ├── linux-security.md
│   ├── permissions.md
│   ├── ownership.md
│   ├── chmod.md
│   ├── chown.md
│   ├── sudoers.md
│   ├── ufw.md
│   ├── iptables.md
│   ├── nftables.md
│   ├── fail2ban.md
│   ├── apparmor.md
│   └── security-checklist.md
│
├── shell-scripting/
│   ├── scripting-introduction.md
│   ├── variables.md
│   ├── arrays.md
│   ├── operators.md
│   ├── conditions.md
│   ├── loops.md
│   ├── functions.md
│   ├── arguments.md
│   ├── exit-codes.md
│   ├── debugging.md
│   └── practical-scripts.md
│
├── git/
│   ├── git-basics.md
│   ├── git-config.md
│   ├── branching.md
│   ├── merge.md
│   ├── rebase.md
│   ├── tags.md
│   ├── stash.md
│   ├── github-cli.md
│   └── ssh-with-github.md
│
├── development-tools/
│   ├── vim.md
│   ├── neovim.md
│   ├── vscode.md
│   ├── nano.md
│   ├── gcc.md
│   ├── make.md
│   ├── cmake.md
│   ├── gdb.md
│   ├── strace.md
│   └── ltrace.md
│
├── programming-environments/
│   ├── python.md
│   ├── nodejs.md
│   ├── php.md
│   ├── java.md
│   ├── go.md
│   ├── rust.md
│   └── virtual-environments.md
│
├── containers/
│   ├── docker.md
│   ├── docker-compose.md
│   ├── container-networking.md
│   ├── container-storage.md
│   ├── docker-security.md
│   └── podman.md
│
├── kubernetes/
│   ├── kubernetes-basics.md
│   ├── pods.md
│   ├── deployments.md
│   ├── services.md
│   ├── ingress.md
│   ├── volumes.md
│   ├── configmaps.md
│   ├── secrets.md
│   └── kubectl.md
│
├── devops/
│   ├── ci-cd.md
│   ├── github-actions.md
│   ├── gitlab-ci.md
│   ├── jenkins.md
│   ├── ansible.md
│   ├── terraform.md
│   ├── monitoring.md
│   ├── prometheus.md
│   └── grafana.md
│
├── cloud/
│   ├── aws.md
│   ├── azure.md
│   ├── gcp.md
│   ├── digitalocean.md
│   ├── vps-management.md
│   ├── cloud-networking.md
│   └── cloud-security.md
│
├── performance/
│   ├── cpu.md
│   ├── memory.md
│   ├── disk-io.md
│   ├── profiling.md
│   ├── optimization.md
│   └── benchmarking.md
│
├── troubleshooting/
│   ├── boot-problems.md
│   ├── networking-issues.md
│   ├── package-errors.md
│   ├── service-failures.md
│   ├── disk-space-issues.md
│   ├── permission-errors.md
│   └── debugging-workflow.md
│
├── interview-preparation/
│   ├── linux-interview-questions.md
│   ├── devops-interview-questions.md
│   ├── networking-interview-questions.md
│   └── system-design-linux.md
│
├── cheatsheets/
│   ├── linux-cheatsheet.md
│   ├── bash-cheatsheet.md
│   ├── apt-cheatsheet.md
│   ├── networking-cheatsheet.md
│   ├── docker-cheatsheet.md
│   ├── kubernetes-cheatsheet.md
│   └── git-cheatsheet.md
│
└── assets/
    ├── images/
    ├── diagrams/
    └── screenshots/
```