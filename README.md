# Make your bash prompt informative
I am working with multiple cloud environments, terraform projects, git repositories and kubernetes clusters.
So, it hard to keep in mind which environment is set in a given time.
To minimise risk of deploing staff in undesired environment I utilised bash prompt to inform me what is current environement I work with.

# Downloads

* For git - git prompt https://github.com/magicmonty/bash-git-prompt
* For kubernetes - kube ps1 https://github.com/jonmosco/kube-ps1
* To switch between kuberentes clsuters - kubectx and kubens https://github.com/ahmetb/kubectx
* To check what my current AWS account - AWS_PROFILE environment variable. 

# Bash prompt
Option 1. All informaton on the second line
```
source ~/.bash-git-prompt/gitprompt.sh
source ~/.kube-ps1/kube-ps1.sh
GIT_PROMPT_START="\u@\h:\w"
GIT_PROMPT_END="\naws:\$AWS_PROFILE ${ResetColor} \$(kube_ps1)\n$"

```

Option 2. All informaton on the first line
```
source ~/.bash-git-prompt/gitprompt.sh
source ~/.kube-ps1/kube-ps1.sh
GIT_PROMPT_START="\u@\h:\W\e[93m aws:\$AWS_PROFILE\e[39m ${ResetColor} \$(kube_ps1)"

```

# Bash completion
What also come in handy is bash completion for git, aws, kubectl and others.


# Downloads
* Bash completion
* Bash completion for git 
* bash completion aws
* bash completion kubectl

# Alias for kubectl with autocompletion
```
source <(kubectl completion bash)
alias k=kubectl
complete -o default -F __start_kubectl k
```
