# Good_Auditor_Agent
A multi-agent AI system that provides professional audit consultation based on ISO 19011:2018 standards.

## What This Does

This program creates three AI agents that work together to help you with audit questions:
- **Senior Auditor**: Provides expert guidance
- **Compliance Officer**: Ensures ISO 19011:2018 compliance
- **Report Writer**: Creates professional audit reports

## Prerequisites

1. **Python 3.8+** installed on your computer
2. **OpenAI API Key** (you need to get this from OpenAI)

## Step-by-Step Setup

### Step 1: Install Required Packages

Open your terminal/command prompt and run:

```bash
pip install python-dotenv autogen-agentchat autogen-ext
```

### Step 2: Get Your OpenAI API Key

1. Go to [OpenAI's website](https://platform.openai.com/)
2. Create an account or log in
3. Go to API Keys section
4. Create a new API key
5. Copy the key (it looks like: `sk-...`)

### Step 3: Create Environment File

1. In the same folder as `main.py`, create a new file called `.env`
2. Open the `.env` file and add your API key:

```
OPENAI_API_KEY=sk-your-actual-api-key-here
```

**Important**: Replace `sk-your-actual-api-key-here` with your real API key!

### Step 4: Run the Program

In your terminal, navigate to the project folder and run:

```bash
python main.py
```

## How to Use

### Interactive Mode (Default)

When you run the program, you'll see:

```
======================================================================
GOOD AUDITOR AGENT - ISO 19011:2018 Expert System
======================================================================

Commands: 'quit'/'exit' to stop, 'clear' for new session

🔍 Audit Question: 
```

**What to do:**
1. Type your audit question and press Enter
2. Wait for the AI agents to discuss and provide answers
3. Type another question or use commands:
   - `quit` or `exit` - Stop the program
   - `clear` - Start a fresh conversation

### Example Questions You Can Ask

- "How do I plan a risk-based audit for ISO 9001?"
- "What documentation do I need for an internal audit?"
- "How should I handle non-conformities during an audit?"
- "What are the key principles of ISO 19011:2018?"

### Example Mode

To run with a pre-built example question, change this line in `main.py`:

```python
asyncio.run(main(interactive=False))  # Change True to False
```

## Configuration Options

You can modify settings in the `Config` class:

```python
@dataclass
class Config:
    model: str = "gpt-5-mini-2025-08-07"  # AI model to use
    max_msg: int = 6                       # Max messages per discussion
    max_turn: int = 2                      # Max conversation rounds
```

## Troubleshooting

### "OPENAI_API_KEY required" Error
- Make sure your `.env` file exists
- Check that your API key is correct
- Ensure there are no extra spaces in the `.env` file

### Import Errors
- Run `pip install python-dotenv autogen-agentchat autogen-ext` again
- Make sure you're using Python 3.8 or newer

### Connection Errors
- Check your internet connection
- Verify your OpenAI API key is valid and has credits

## File Structure

```
good_auditor_agent/
├── main.py          # Main program file
├── .env             # Your API key (create this)
└── README.md        # This file
```

## What Each Part Does

- **Config**: Stores settings and loads your API key
- **Messages**: Contains the instructions for each AI agent
- **AuditSystem**: Creates and manages the AI agents
- **InteractiveAudit**: Handles user input and display
- **main()**: Starts everything up

## Need Help?

If you get stuck:
1. Check that all files are in the right place
2. Make sure your API key is correct
3. Try running the example mode first
4. Check your internet connection

The program follows ISO 19011:2018 standards for audit guidance and maintains professional audit principles throughout all interactions.
