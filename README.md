# Ansible Prometheus-Stack

Simple Ansible playbook to install the prometheus-stack.  
The following componentes will be installed:  
* node-exporter
* prometheus-server
* grafana-server

Pre-configured credentials:
* Node Exporter
  * Basic auth `prometheus-scraper` - `changeMe0815!`
* Prometheus
  * Basic auth `prometheus` - `changeMe0815!`
* Grafana
  * Default admin `admin` - `changeMe0815!`

## Usage

**Prepare Inventory**  
Update the inventory to your needs.

**Create Virtual Environment**
```
python3 -m venv .ansible2.9
source .ansible2.9/bin/activate
python3 -m pip install --upgrade pip
python3 -m pip install ansible==2.9
python3 -m pip install passlib bcrypt
ansible-galaxy install -r requirements.yml --force
```

**Deploy Ansible**
```
ansible-playbook -i inventory main.yml
```