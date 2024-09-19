**Graded assignment on Automated Testing and Linux and Shell Scripting**

This file contains the detailed steps performed to complete each task


**Initial Setup**
  1. Open PowerShell in elevated mode
  2. type wsl and press enter
  3. created new folder "bashAssignment" to store all the scripts
     mkdir -p bashAssignment
     cd bashAssignment

**1. Create a Directory Structure**
  1.   /home/user/

       ├── projects/

       │   ├── project1/

       │   ├── project2/

       │   └── project3/

       ├── documents/

       └── downloads/

  2. Created a file "directoryStructure.sh" using
     touch directoryStructure.sh
  3. Provided execution permissions using
     chmod +x directoryStructure.sh 
  4. opened in vi editor using
     vi directoryStructure.sh
  5. used mkdir -p <directory> to create the depicted directory structure
       -p --> to create parent directories if not exists
  6. Executed script using ./directoryStructure.sh
  7. Viewed the directory structure using
     tree home

**2. File Backup**
  1. Created a file "fileBackup.sh" using
     touch fileBackup.sh
  2. Provided execution permissions using
     chmod +x fileBackup.sh
  3. opened in vi editor using
     vi fileBackup.sh
  4. Script checks whether the directory name is passed as an argument and it is valid
  5. If valid, creates backup directory with current timestamp
  6. The script uses the find command to locate all .txt files in the specified directory and copies them to the newly created backup directory
  7. run the script using
     ./fileBackup.sh <directoryname>

**3. User Information**
  1. Created a file "userInfo.sh" using
     touch userInfo.sh
  2. Provided execution permissions using
     chmod +x userInfo.sh
  3. opened in vi editor using
     vi userInfo.sh
  4. used $(whoamI), $id, $HOME, $SHELL commands to extract user information
  5. run the script using
     ./userInfo.sh

**4. Disk Usage Alert**
  1. Created a file "diskUsageAlert.sh" using
     touch diskUsageAlert.sh
  2. Provided execution permissions using
     chmod +x diskUsageAlert.sh
  3. opened in vi editor using
     vi diskUsageAlert.sh
  4. used
     df /: Checks disk usage for the root filesystem.
     grep /: Filters the output to include only the line for the root filesystem.
     awk '{ print $5 }': Extracts the usage percentage (fifth column).
     sed 's/%//g': Removes the percent sign from the output.
     If the disk usage exceeds the threshold, it sends an email to the specified administrator email address.
  5. Before running the script, make sure mail utilities library is installed to verify the mailing functionality
     sudo apt-get install mailutils
  6. run the script using
     ./diskUsageAlert.sh

**5. File Permission Checker**
  1. Created a file "filePermissions.sh" using
     touch filePermissions.sh
  2. Provided execution permissions using
     chmod +x filePermissions.sh
  3. opened in vi editor using
     vi filePermissions.sh
  4. Checked if a file argument is provided. Verified if the specified file exists. Used -r, -w, and -x flags to check for read, write, and     
     execute permissions, respectively. Based on the checks, it outputs whether each permission is granted or denied
  5. run the script using
     ./filePermissions.sh <filename>

**6. Automated Backup**
  1. Created a file "automatedBackup.sh" using
     touch automatedBackup.sh
  2. Provided execution permissions using
     chmod +x automatedBackup.sh
  3. opened in vi editor using
     vi automatedBackup.sh
  4. Checked if source exists. If yes, created backup folder and used tar -czf command to create a compressed tarball (.tar.gz) of the documents directory. The -C      option changes to the source directory before creating the archive, ensuring that the directory structure is preserved
  5. run the script using
     ./automatedBackup
  6. To schedule cron job,
     type "crontab -e" --> opens cron editor
      0 <timeofday> * * * /path/to/script --> enter this line, save and close. This will run the script every hour

**7. Process Monitor**
  1. Created a file "processMonitor.sh" using
     touch processMonitor.sh
  2. Provided execution permissions using
     chmod +x processMonitor.sh
  3. opened in vi editor using
     vi processMonitor.sh
  4. Checked if processName is passed as argument. If yes, verified whether its a valid process. If yes, used pgrep -x, which searches for processes by name.
     If the process is not running, it starts the process using systemctl start.
     It logs the action with a timestamp to the specified log file (/var/log/process_monitor.log).
  5. run the script using
     ./processMonitor.sh apache2

**8. Text File Analysis**
  1. Created a file "textFileAnalysis.sh" using
     touch textFileAnalysis.sh
  2. Provided execution permissions using
     chmod +x textFileAnalysis.sh
  3. opened in vi editor using
     vi textFileAnalysis.sh
  4. Checked if a file argument is provided and if the specified file in .txt format exists.
     Used wc (Word Count) command
     wc -l counts the number of lines.
     wc -w counts the number of words.
     wc -c counts the number of characters.
  5. run the script using
     ./textFileAnalysis.sh file.txt

**9. System Information Report**
  1. Created a file "sysInfoReport.sh" using
     touch sysInfoReport.sh
  2. Provided execution permissions using
     chmod +x sysInfoReport.sh
  3. opened in vi editor using
     vi sysInfoReport.sh
  4. Used below commands to find System Information
      uptime : Displays how long the system has been running.
      free -h: Displays memory usage in a human-readable format.
      top -bn1 | grep "Cpu(s)": Uses top to get CPU usage statistics.
      df -h: Displays the disk space usage for all mounted filesystems in a human-readable format.
      ps aux --sort=-%mem : Displays  memory-consuming processes.
  5. run the script using
     ./sysInfoReport.sh

**10. Simple Calculator**
  1. Created a file "simpleCalculator.sh" using
     touch simpleCalculator.sh
  2. Provided execution permissions using
     chmod +x simpleCalculator.sh
  3. opened in vi editor using
     vi simpleCalculator.sh
  4. Used case statement to perform arithmetic operations
  5. run the script using
     ./simpleCalculator.sh 1 2 +
