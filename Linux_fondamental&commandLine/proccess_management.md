## Managing service with Systemd

   > - Systemdctl start : Start a Service.
   > - Systemdctl status: Check the status of a service.
   > - Systemdctl enable: Enable a service to start on boot.
   > - systemctl stop service: Stop a service.

## Journaling and Logs

systemd uses journald to manage logs for services and system processes.
View logs using journalctl:
   > - journalctl -b: View logs from the current boot.
   > - journalctl -u: View logs for a specific service.

#### Understanding Processes in Linux:

> - A process is a running instance of a program.
> - Processes can be in the foreground (interacting with users) or background
(running without user interaction).
> - Processes have different priorities, which can be adjusted with nice and renice.
> -Key Concepts:
   > - Foreground vs. Background processes.
   > - Process ID (PID): Every process has a unique identifier.
   > -  Parent and child processes: Processes can create other processes.

##### nice: Adjusts the priority of a process when it starts.
> - Lower nice value = higher priority.

##### renice: Changes the priority of an already running process.
Example commands:
   > - nice -n 10 myscript.sh: Start a script with lower priority.
   > - renice -n -5 1234: Change the priority of process 1234 to a higher priority.

Using top and htop to Monitor Processes:
> - top: Displays real-time system summary, including CPU, memory usage, and active processes.
> - Use top to identify resource-hungry processes.
> - htop: An improved, interactive version of top with a more user-friendly interface.
> - Key commands:
   > - top: Start the process monitor.
   > - htop: Start an interactive process monitor.

Viewing and Managing Processes with ps and kill
> -  ps: Lists processes running on the system. Use it to get details about processes.
   > - ps aux: List all running processes with details.
> -  kill: Sends signals to terminate or control processes.
   > - kill -9 PID: Forcefully terminate a process.
> -  Key Concepts:
   > -  PID: Process ID, used to manage specific processes.
   > - Signals: Control how processes are managed, such as termination (SIGKILL) or stopping (SIGSTOP).


## Advanced Monitoring with strace and lsof

strace: Monitors system calls made by a process. Useful for
troubleshooting:
○ strace -p PID: Monitor system calls for a specific process.
● lsof: Lists open files and network connections for a process:
○ lsof -p PID: List files opened by a process.
● Use cases:
○ strace helps identify why a process is stuck or misbehaving.
○ lsof helps track what files or sockets are being used by a process.
asAt 5zesedacä-
a eswaems l x