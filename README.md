#!/bin/bash

# Installation script for setting up admin server

# Define tools and their corresponding package names
name="Zo"

tool1="grafana"         # Monitoring tool
package1="grafana.aarch64"

tool2="apache2"         # Web server
package2="httpd.aarch64"

tool3="git"             # Version control system
package3="git.aarch64"

tool4="mysql"           # Database server (MySQL)
package4="mysql-server.aarch64"

tool5="postgresql"      # Database server (PostgreSQL)
package5="postgresql.aarch64"

tool6="docker"          # Containerization platform
package6="podman-docker.noarch"

tool7="ansible"         # Configuration management tool
package7="ansible-core.aarch64"

tool8="rsyslog"         # Logging system
package8="rsyslog.aarch64"

tool9="nmap"            # Network scanner
package9="nmap.aarch64"

tool10="ufw"            # Firewall utility
package10="net-tools.aarch64"

# Name is interchangeable and can be modified at the start of the script
echo "Running admin server setup for $name"

# Function to check if each tool is installed and install it if not
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

# Check for each package installation
# Each section corresponds to a specific role or functionality of the server

# Monitoring tool
check_install "$tool1" "$package1"

# Web server
check_install "$tool2" "$package2"

# Version control system
check_install "$tool3" "$package3"

# Database server (MySQL)
check_install "$tool4" "$package4"

# Database server (PostgreSQL)
check_install "$tool5" "$package5"

# Containerization platform
check_install "$tool6" "$package6"

# Configuration management tool
check_install "$tool7" "$package7"

# Logging system
check_install "$tool8" "$package8"

# Network scanner
check_install "$tool9" "$package9"

# Firewall utility
check_install "$tool10" "$package10"
```

I've added comments to each section of the script to define roles for the corresponding tools/packages. You can now upload this script to GitHub as a repository.
