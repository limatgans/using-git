## What is Git?
In simple terms, **Git** is a *free* and *open source* *distributed* **version control system**.

A **Version Control System (VCS)** manages all the changes to your project and thereby allows you to have track of all the changes by different contributors to your project.

### Central vs Distributed VCS

Central VCS (such as CVS, Subversion, and Perforce) have a single server that contains all the versioned files, and a number of clients that check out files (snapshots) from that central place. One of major downside is failure of the central server with no proper backups. The entire history of the project is gone except whatever single snapshots people happen to have on their local machines

On the other hand, Distributed VCS (such as **Git**, Mercurial, Bazaar or Darcs) fully mirrors the project from server onto the client machine (including the entire history) instead of just snapshots. In case of server failure, any of the client repositories can be copied back up to the server to restore it 

- Next - [Installing GIT](./Installing-GIT.md)
- Previous - [Table of Contents](./index.md)