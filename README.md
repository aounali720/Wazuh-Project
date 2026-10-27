# Wazuh manager and agent lab

I set up a Wazuh manager on a cloud Ubuntu instance and enrolled Windows and Ubuntu lab machines as agents. The aim was to see how endpoint events reach a central dashboard and to troubleshoot agent-manager communication.

## Lab notes

- [Install the manager](Wazuh-AIO-cloud-instance.md) — all-in-one installation, dashboard access and basic server checks.
- [Connect the agents](Settingup-wazuh-agents.md) — Windows and Ubuntu enrollment, manager address settings and service troubleshooting.

**Environment:** cloud Ubuntu VM, Wazuh manager/dashboard, Windows and Ubuntu test endpoints.

The documents are historical setup notes. They are not a claim of production detection coverage. Restrict dashboard and manager access before exposing a Wazuh server, and consult the [official installation guide](https://documentation.wazuh.com/current/installation-guide/index.html) for current package and port requirements.
