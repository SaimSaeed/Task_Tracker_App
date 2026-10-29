# Task Tracker

## Project Goal
Build a command-line **Task Tracker** application that allows users to manage their daily tasks. The application stores all tasks in a JSON file and retrieves them when the program runs again, ensuring tasks persist between sessions.

## Features

### Core Functionality
- **Add Tasks**: Create new tasks with a title. Tasks are stored as "Pending" by default.
- **View Tasks**: Display a numbered list of all tasks with their current status (Pending or Done).
- **Complete Tasks**: Mark tasks as "Done" by selecting them by number.
- **Delete Tasks**: Remove tasks from the list by selecting them by number.
- **Save & Load**: Automatically save all changes to `tasks.json` and load existing tasks on startup.
- **Menu Loop**: Keep the program running until the user selects "Exit."

### Error Handling
The application gracefully handles:
- Empty task titles (prevents adding blank tasks)
- Invalid menu choices (asks user to enter 1-5)
- Invalid task numbers (checks if the number is within the list range)
- Missing JSON file (starts with an empty task list if the file doesn't exist)
- File read/write errors (displays helpful error messages)

## How to Run

### Prerequisites
- Python 3.x installed on your system

### Steps
1. **Download or clone** the `mini_task_tracker.py` file to your computer.
2. **Open a terminal** (or command prompt) and navigate to the folder containing the file.
3. **Run the program**:
   ```bash
   python mini_task_tracker.py
   ```
4. **Follow the menu prompts**:
   - Enter `1` to add a task
   - Enter `2` to view all tasks
   - Enter `3` to mark a task as complete
   - Enter `4` to delete a task
   - Enter `5` to exit the program

### Sample Interaction
```
Loading tasks...
No existing tasks. Starting fresh.

--- TASK TRACKER ---
1. Add 2. View 3. Complete 4. Delete 5. Exit
Choice: 1
Task title: Read notes
Tasks saved successfully.
Task added.

--- TASK TRACKER ---
1. Add 2. View 3. Complete 4. Delete 5. Exit
Choice: 2
1. Read notes [Pending]

--- TASK TRACKER ---
1. Add 2. View 3. Complete 4. Delete 5. Exit
Choice: 3
1. Read notes [Pending]
Task number: 1
Task completed.
Tasks saved successfully.

--- TASK TRACKER ---
1. Add 2. View 3. Complete 4. Delete 5. Exit
Choice: 2
1. Read notes [Done]

--- TASK TRACKER ---
1. Add 2. View 3. Complete 4. Delete 5. Exit
Choice: 5
Goodbye!
```

## File Structure

### mini_task_tracker.py
The main Python script containing:
- `load_tasks()`: Loads tasks from the JSON file at startup
- `save_tasks(tasks)`: Saves the current task list to JSON
- `add_task(tasks)`: Adds a new task with validation
- `view_tasks(tasks)`: Displays all tasks with their status
- `complete_task(tasks)`: Marks a task as done
- `delete_task(tasks)`: Removes a task from the list
- `menu(tasks)`: Displays the main menu and handles user input
- `main()`: Initializes the program and starts the menu loop

### tasks.json
A JSON file created automatically to store all tasks. Each task is an object with:
```json
{
  "title": "Task name",
  "done": false
}
```

### README.md
This file, containing project documentation and usage instructions.

## Usage Tips

1. **Persistent Storage**: Your tasks are saved automatically after each action (add, complete, or delete). They will be available the next time you run the program.

2. **Google Colab**: If running in Google Colab, download the `tasks.json` file to your computer or save it to Google Drive for permanent storage, as files in the Colab runtime are temporary.

3. **Error Messages**: The program provides clear feedback for incorrect inputs. Follow the prompts and try again.

## Future Enhancements
- Add task priorities (High, Medium, Low)
- Set due dates for tasks
- Filter tasks by status or priority
- Export tasks to CSV or PDF
- Add categories or tags for tasks

## Author
Created as part of the AI Engineering Course - Week 1, Day 2

## License
This project is open source and available for educational purposes.
