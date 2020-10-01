# Kubeconfig switchers
## What is it
This is a set of two tools that will allow usage of more than one kubeconfig files without being as burdensome.  Each provides a menu that lists the entries from your `~/.kube` directory and lists them for selection, and then copies the selected kubeconfig to `~/.kube/config`

kr - [K]ubeconfig-switcher [R]ofi: displays the selection using rofi

kf - [K]ubeconfig-switcher [f]uzzy: displays the selection in terminal using a fuzzy picker

## Configuration
There is some up front prep work needed in order to use this tool.

This script uses the `~/.kube/config` method to configure kubeconfigs.  Best to **rename it** before using this tool.

Prereq: You're going to want to name your kubeconfig files as "`config.{desc}`" where `{desc}` is a descriptive string.

For example:
```
> ls ~/.kube
 .                              config.aws-config-number-1
 ..                             config.gcp-config-east-1
 cache                          config.gcp-config-east-2
 config.another.cluster         config.gcp-config-west-1
 config.aws-config-number-2
```

Installation:
```
git clone git@github.com:phwelo/kubeswitchers.git
cd kubeswitchers
chmod +x kr kf
mv k? ~/.local/bin
pip -r requirements.txt
cd ..
rm -rf kubeswitchers
```
if you don't have a `~/.local/bin`, you'll need to create it and add to `PATH` or use sudo and move it to `/usr/bin` or something.
