# Exno.7-Prompt-Engineering
# Date:
# Register no:212222050055
# Aim: To Develop a prompt-based application tailored to their personal needs, fostering creativity and practical problem-solving skills while leveraging the capabilities of large language models.

# Objective:
The objective of this exercise is to demonstrate the development of a prompt-based application using ChatGPT. The application will focus on organizing daily tasks and will showcase the progression from simple to more advanced prompt designs, illustrating how to harness the capabilities of a large language model effectively.

# Algorithm:
Step 1: Define the Problem
Create a task management system where users can input their daily tasks, and the model will help organize and prioritize those tasks.

Key functionalities:

Task Input

Task Categorization

Prioritization

Task Summary with a suggested timeline

Step 2: Create Simple Prompts
Sample Prompt 1:

"Please list your tasks for today."

Step 3: Implement Categorization
Sample Prompt 2:

"Please categorize these tasks into work, personal, and miscellaneous categories. Tasks: [task list]"

Step 4: Task Prioritization
Sample Prompt 3:

"Please prioritize the following tasks based on their urgency and importance: [task list]. Include a brief reason for the prioritization."

Step 5: Suggest a Task Plan
Sample Prompt 4:

"Please create a task plan for the following tasks, suggesting the best order to complete them, the estimated time for each, and an ideal timeline."

Step 6: Feedback and Optimization
Based on user feedback, optimize and refine the prompts to provide better task management, suggestions, and improvements.

Code Implementation:
Prerequisites:
Python 3.x

OpenAI API Key

Installing OpenAI Python Library:
bash
Copy
Edit
pip install openai
Python Code:
python
Copy
Edit
import openai

# Function to initialize OpenAI API
def initialize_openai():
    openai.api_key = "YOUR_OPENAI_API_KEY"

# Function to create prompt-based tasks management
def organize_tasks(tasks):
    # Simple task input
    prompt_input = f"Please list your tasks for today: {tasks}"

    # Categorizing tasks
    prompt_categorization = f"Please categorize these tasks into work, personal, and miscellaneous categories: {tasks}"

    # Prioritizing tasks
    prompt_prioritization = f"Please prioritize the following tasks based on their urgency and importance: {tasks}"

    # Task plan suggestion
    prompt_plan = f"Please create a task plan for the following tasks, suggesting the best order to complete them, the estimated time for each, and an ideal timeline: {tasks}"

    return prompt_input, prompt_categorization, prompt_prioritization, prompt_plan

# Function to call OpenAI API with prompts
def call_openai_api(prompt):
    response = openai.Completion.create(
        engine="text-davinci-003",  # You can use "gpt-3.5-turbo" or another model
        prompt=prompt,
        max_tokens=150,
        n=1,
        stop=None,
        temperature=0.7
    )
    return response.choices[0].text.strip()

# Main function to organize tasks using ChatGPT
def main():
    # Example tasks list (in real-world use, this would be input by the user)
    tasks = [
        "Finish work report",
        "Buy groceries",
        "Call the dentist",
        "Prepare for the meeting",
        "Pick up dry cleaning"
    ]
    
    initialize_openai()
    
    # Generate the prompts
    prompt_input, prompt_categorization, prompt_prioritization, prompt_plan = organize_tasks(tasks)
    
    # Get responses from OpenAI API
    response_input = call_openai_api(prompt_input)
    response_categorization = call_openai_api(prompt_categorization)
    response_prioritization = call_openai_api(prompt_prioritization)
    response_plan = call_openai_api(prompt_plan)
    
    # Display the results
    print("Input Tasks: ", response_input)
    print("\nCategorized Tasks: ", response_categorization)
    print("\nPrioritized Tasks: ", response_prioritization)
    print("\nSuggested Task Plan: ", response_plan)

if __name__ == "__main__":
    main()
# Explanation of Code:
initialize_openai(): Initializes the OpenAI API with a given API key.

organize_tasks(): Generates four prompts to handle task input, categorization, prioritization, and scheduling.

call_openai_api(): Sends the prompt to the OpenAI API and retrieves the response.

main(): Main execution block that inputs the tasks, calls the organizing functions, and displays the results.

# verification:
Upon execution, the system should output:

Input Tasks: The user’s original list of tasks.

Categorized Tasks: Grouped into work, personal, and miscellaneous.

Prioritized Tasks: Ordered by urgency and importance.

Suggested Task Plan: Structured schedule with time and order.

# Conclusion:
The prompt-based task management system effectively utilizes ChatGPT to automate and optimize task organization. By designing purposeful prompts, the model assists users in categorizing, prioritizing, and planning their daily tasks. Further enhancements could include reminder features, progress tracking, or integration with a graphical user interface.






# Result: The Prompt is executed successfully


