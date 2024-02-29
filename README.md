# Process-Monitoring-Automation-Shell-Script

# Bash Process Monitor Script

## Overview

This Bash script is designed to monitor a specific process on a Linux system, ensuring it is always running. If the process unexpectedly stops, the script will automatically restart it. Additionally, it provides instructions for scheduling the script to run at regular intervals using cron jobs.

## Usage

To use the script, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo.git
   ```
2. Navigate to the script directory:
   ```bash
   cd bash_process_monitor
   ```
3. Run the script with the target process name as an argument:
   ```bash
   ./monitor_process.sh <process_name>
   ```

## Functionality

1. **Process Selection:**

   - The script accepts a command-line argument specifying the target process to monitor.

2. **Process Existence Check:**

   - The `check_process_running` function checks if the specified process is currently running on the system.
   - If the process is running, it prints a message indicating its presence.

3. **Restarting the Process:**

   - If the process is not running, the `restart_process` function attempts to restart the process automatically.
   - It prints a message indicating the attempt to restart the process.
   - The script limits the number of restart attempts to prevent infinite looping.

4. **Automation:**

   - To schedule the script to run at regular intervals, use cron jobs or any other appropriate scheduling method.
   - Example cron job entry:
     ```bash
     */5 * * * * /path/to/monitor_process.sh <process_name> >> /var/log/process_monitor.log 2>&1
     ```
     This example runs the script every 5 minutes and redirects output to a log file for review.

5. **Documentation:**

   - The script includes clear and concise comments explaining its logic and functionality.
   - Refer to the comments within the script for detailed explanations of each section.

6. **Bonus:**

   - Implement a notification mechanism to alert administrators if the process requires manual intervention after a certain number of restart attempts. This can be achieved by integrating email or Slack notifications within the script.

## Example Interaction

Refer to the [example_interaction.md](./usr_example_interaction.md) file to see a sample interaction with the script, demonstrating its usage and behavior.

## Notes

- Feel free to customize the script, add more features, or enhance error handling as needed.
- Test the script thoroughly on a test system before deploying it to a production environment to ensure stability and reliability.
- If you encounter any issues or have questions, open an issue in this repository for assistance.
