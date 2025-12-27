1- Managing service with Systemd

   a- Systemdctl start : Start a Service
   b- Systemdctl status: Check the status of a service
   c- Systemdctl enable: Enable a service to start on boot

2- Journaling and Logs

systemd uses journald to manage logs for services and system processes.
View logs using journalctl:
   a- journalctl -b: View logs from the current boot.
   b-  journalctl -u: View logs for a specific service.

