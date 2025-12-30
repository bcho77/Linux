
## File System and Storage Management

A file system manages how data is stored and retrieved from a disk.
Common Linux file systems:
> - ext4: The most common default file system.
> - XFS: Known for handling large files efficiently.
> - Btrfs: Offers advanced features like snapshots and pooling.

## Mounting and Unmounting 

Mounting attaches a file system to a specific directory, making it accessible.
> - Commands:
    1. mount /dev/sda1 /mnt: Mount a file system.
    2. umount /mnt: Unmount a file system.
> - <span style="color:black"> Persistent mounts are configured in /etc/fstab for automatic mounting at boot </span>.

## File System Hierachy

The Linux Filesystem Hierarchy Standard (FHS) defines the directory
structure and contents.
It starts with the root __/__ directory, which contains other key directories like:
Each directory has a specific purpose:
> - /bin: Essential command binaries (e.g., ls, cp).
> - /etc: Configuration files for the system.
> - /usr: User applications and files.
> - /var: Variable files like logs and databases.
> - /root: Home directory for the root user.
> - /tmp: Temporary files.
> - /var/log: System log files.
> - /home: Home directories for non-root users.
> - /mnt: Temporary mount points.
> - /opt: Optional software.
> - /dev: Device files, such as hard drives and USB devices.
> - /proc: Information about running processes.

## Managing Swap Space

Swap space is used as virtual memory when the system runs out of physical RAM.
> - To create a swap file:
    1. fallocate -l 1G /swapfile
    2. mkswap /swapfile
    3. swapon /swapfile
> - Monitor swap usage using the free command.

## Monitoring Storage Usage

> - df: Shows disk space usage.
> - df -h: Shows human-readable disk space usage.
> - du: Shows directory and file sizes.
> - du -sh /var/log: Shows the size of a directory.
> - Quota: Disk space management for users.
> - Best practice: Regularly monitor and clean up disk space to avoid downtime.

## Troubleshooting

> - fsck: A tool for checking and repairing file system errors.
> - fsck /dev/sda1: Check and repair a file system.
> - Use df and du for diagnosing disk space issues.
> - Mounting options: Use options like ro (read-only) or noatime to control mount behavior

## Logical Volume Management

> - LVM allows you to manage and resize storage dynamically.
> - LVM Structure:
> - Physical Volumes (PVs): The physical disks or partitions.
> - Volume Groups (VGs): Groups of physical volumes.
> - Logical Volumes (LVs): The storage units you create and manage.
> - Key benefit: You can resize, add, or remove volumes without rebooting the syste

### Creating and Managing Logical Volumes
#### Example commands:
> - pvcreate /dev/sda1: Create a physical volume.
> - vgcreate myvg /dev/sda1: Create a volume group.
> - lvcreate -L 10G -n mylv myvg: Create a logical volume.
> - mkfs.ext4 /dev/myvg/mylv: Format the logical volume with a file system.
> - mount /dev/myvg/mylv /mnt: Mount the logical volume.
#### Resizing logical volumes:
> - lvextend -L +5G /dev/myvg/mylv: Increase the size of the logical volume.
> - resize2fs /dev/myvg/mylv: Resize the file system to match the logical
volume.

### Monitoring LVM

> - Use vgdisplay to show information about volume groups.
> - Use lvdisplay to check logical volume details.
> -  Example:
    > - vgdisplay myvg
    > - lvdisplay /dev/myvg/mylv
> - Best practice: Regularly monitor volume groups and logical volumes to
ensure they have enough space.

