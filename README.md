# centos9-install-script
This script checks for packages on your cent os server and then installs the missing tools. Its customizable by variables so you can add ass many tools and adjust the echo output any way you would like. 
#!/bin/bash

#installation script for each tool and package can be interchanged with any package 
# Define tools and their corresponding package names
name="Zo"

tool1="grafana"
package1="grafana.aarch64"

tool2="apache2"
package2="httpd.aarch64"

tool3="git"
package3="git.aarch64"

tool4="mysql"
package4="mysql-server.aarch64"

tool5="postgresql"
package5="postgresql.aarch64"

tool6="docker"
package6="podman-docker.noarch"

tool7="ansible"
package7="ansible-core.aarch64"

tool8="rsyslog"
package8="rsyslog.aarch64"

tool9="nmap"
package9="nmap.aarch64"

tool10="ufw"
package10="net-tools.aarch64"

#name is interchangable up top at the start of the script
echo "running admin server set up for $name"

# Check if each tool is installed
check_install() {
    local tool="$1"
    local package="$2"
    if command -v "$tool" &> /dev/null; then
        echo "$tool already installed"
    else
        echo "$tool not installed, installing..."
        sudo yum install "$package"
    fi
}

# Check for each package install
check_install "$tool1" "$package1"
check_install "$tool2" "$package2"
check_install "$tool3" "$package3"
check_install "$tool4" "$package4"
check_install "$tool5" "$package5"
check_install "$tool6" "$package6"
check_install "$tool7" "$package7"
check_install "$tool8" "$package8"
check_install "$tool9" "$package9"
check_install "$tool10" "$package10"
