- This exploit relies on the Task Scheduler GUI opening as administrator by default without any user prompts.

### SCHTASKS
- The Task Scheduler CLI tool.
```Powershell
SCHTASKS /CREATE /SC MINUTE /TN "CMD task" /TR "C:\Windows\System32\cmd.exe" /RL HIGHEST
```
- This command creates a task:
	- `/TN` (Task Name) - `CMD Task`
	- `/SC` (Schedule Type) - `MINUTE` (Run every minute)
	- `/TR` (Task Run) - `"C:\Windows\System32\cmd.exe"` (The `.exe` file)
	- `/RL` (Level) - `Highest` (Scheduled tasks will be ran with the highest level of privileges)
- By default when tasks are created in the cli tool, they will be set to `LIMITED` level. To escalate the level to `HIGHEST` we require an administrator password.

### Task Scheduler GUI
- On an admin account, the Task Scheduler GUI opens with administrator privilege without a user prompt.
- This allows us to create a task that can run with administrator privileges without knowing the password. Such a task will not give a user prompt.


### Exploit
- Open the Task Scheduler GUI and navigate to the `Task Scheduler Library`![](Attachments/Pasted%20image%2020240801104859.png)
- In the right click menu, click on `Create New Task`.
- In the `General` Tab
	- Assign a name to the task. ( `CMD Task` )
	- Select the option to `Run with highest privileges`
	- In the `Configure for` drop down menu, select Windows 10 ![](Attachments/Pasted%20image%2020240801105221.png)
- In the `Actions` Tab
	- Click on `New..`
	- Set the path to the `"C:\Windows\System32\cmd.exe"` and click OK.![](Attachments/Pasted%20image%2020240801105559.png)
	- `Actions` Tab![](Attachments/Pasted%20image%2020240801110133.png)
- In the `Triggers` Tab
	- Click on `New..`
	- Set the task to repeat every minute, indefinitely. ![](Attachments/Pasted%20image%2020240801110656.png)
	- `Triggers` Tab![](Attachments/Pasted%20image%2020240801110815.png)
- Leave all the other menus on default settings and click OK to create the task.
- Command Prompt opens with administrator privilege at the specified time![](Attachments/Pasted%20image%2020240801111224.png)