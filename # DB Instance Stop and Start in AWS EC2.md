# DB Instance Stop and Start in AWS EC2

- Login to DB instance (Example: dev-coredb)
- Connect to postgres user
  - **sudo su - postgres**
- Stop Command for postgres:
  - **/usr/lib/postgresql/10/bin/pg_ctl -D $PGDATA stop**
  - **$PGDATA** = **/opt/postgres/coredb/10** (data_directory).
- Start Command for postgres:
  - **/usr/lib/postgresql/10/bin/pg_ctl -D $PGDATA start**
- Status Command for postgres:
  - **/usr/lib/postgresql/10/bin/pg_ctl -D $PGDATA status**
    - **Or**
  - **pg_lsclusters**

# Attach new volumes to DB Instance

- Connect to root user
  - **sudo su -**
- **df -hP**
- unmount data disk mount point
  - **umount /opt/postgres**
    - **fuser -km /dev/md127 ---** to kill all the running processes for that file system.
- stop raid/mdadm
  - **mdadm --stop /dev/md127**
- Go to aws console and detach volumes for respective servers.

- Go to the volumes tab in AWS and search with the respective **hostname** and right click on each volume, detach the volumes.
- create volumes using current days **prod-coredb or prod-cortaldb** snapshots.

- Go to the snapshots tab in AWS and search with the **prod-coredb** and right click on each snapshot, create the volume for respective server.
- Attach newly created volumes to respective servers.
- Check if the raid is configured for new disks on the respective server.
  - **cat /proc/mdstat**
  - if raid is not active then assemble by using below command
    - **mdadm --assemble /dev/md127 /dev/xvd{f..m}** --- provide disk range as per new disks attached
- Start xfs_repair against new raid -- May take 15-20 minutes
  - **xfs_repair -L /dev/md127**
- Once above step completed mount new raid on /opt/postgres
  - **mount /dev/md127 /opt/postgres**