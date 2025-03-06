# 📊 Demonstration Data

## Demonstration Data

Every aspect of our platform is designed to generate high-quality training data for multimodal computer-use agents. From AI-generated tasks to expert demonstrations, we capture comprehensive data that helps train AI to understand and replicate human computer interactions.

### Demonstration Files Structure

Each recorded demonstration consists of multiple files:

1. **input\_log.jsonl** - Detailed event log of all user interactions
2. **meta.json** - Metadata and configuration information about the demonstration
3. **recording.mp4** - Video recording of the screen during the demonstration

When you record a demonstration in the Training Gym, the system captures all your interactions in a standardized JSON format. Each user interaction is saved as a separate event in a JSONL file (JSON Lines format) called `input_log.jsonl`. Understanding this format can help you create more effective demonstrations.

#### Event Structure

Each recorded event has the following structure:

```json
{
  "event": "eventType",
  "data": {
    // Event-specific properties
  },
  "time": 1234567890
}
```

* **event**: The type of interaction (e.g., mousemove, mousedown, keydown)
* **data**: Object containing event-specific details
* **time**: Timestamp in milliseconds when the event occurred

#### Event Types

The system records the following types of events:

**Accessibility Tree Events (Windows)**

1.  **axtree**

    ```json
    {
      "event": "axtree",
      "data": {
        "duration": 5645,
        "focused_element": {
          "bbox": {
            "height": 600,
            "width": 800,
            "x": 722,
            "y": 335
          },
          "children": [],
          "description": "",
          "name": "",
          "role": "Pane",
          "states": {
            "enabled": true,
            "keyboard_focusable": false,
            "visible": true
          },
          "value": ""
        },
        "queries": {
          "cursor": {
            "element": { /* Element details */ },
            "position": { "x": 1270, "y": 688 }
          },
          "random1": {
            "element": { /* Element details */ },
            "position": { "x": 378, "y": 400 }
          },
          "random2": {
            "element": { /* Element details */ },
            "position": { "x": 1985, "y": 813 }
          }
        },
        "tree": [
          /* Array of UI elements and their properties */
        ]
      },
      "time": 1741119497902
    }
    ```

    Provides comprehensive information about the accessibility tree, capturing the structure and properties of all on-screen elements from every open application.

    * **duration**: Time in milliseconds that the scan took
    * **focused\_element**: Details about the currently focused UI element
    * **queries**: Information about elements at specific positions
    * **tree**: Full hierarchical structure of all visible UI elements, including:
      * **bbox**: Bounding box (position and dimensions)
      * **children**: Nested UI elements
      * **description**: Element description
      * **name**: Element name
      * **role**: Element type (e.g., "Pane", "Text", "Button", "Image")
      * **states**: Element properties (enabled, focusable, visible)
      * **value**: Element content value

**Mouse Events**

1.  **mousemove**

    ```json
    {
      "event": "mousemove",
      "data": {
        "x": 123,
        "y": 456
      },
      "time": 1234567890
    }
    ```

    Tracks the mouse cursor position on screen.
2.  **mousedown**

    ```json
    {
      "event": "mousedown",
      "data": {
        "x": 123,
        "y": 456,
        "button": "Left"
      },
      "time": 1234567890
    }
    ```

    Recorded when a mouse button is pressed.
3.  **mouseup**

    ```json
    {
      "event": "mouseup",
      "data": {
        "x": 123,
        "y": 456,
        "button": "Left"
      },
      "time": 1234567890
    }
    ```

    Recorded when a mouse button is released.
4.  **mousewheel**

    ```json
    {
      "event": "mousewheel",
      "data": {
        "delta": -120
      },
      "time": 1234567890
    }
    ```

    Tracks scrolling with positive values for scrolling down and negative for scrolling up.

**Keyboard Events**

1.  **keydown**

    ```json
    {
      "event": "keydown",
      "data": {
        "key": "A"
      },
      "time": 1234567890
    }
    ```

    Recorded when a key is pressed.
2.  **keyup**

    ```json
    {
      "event": "keyup",
      "data": {
        "key": "A"
      },
      "time": 1234567890
    }
    ```

    Recorded when a key is released.

### Key Identifiers

The system supports both Windows and Mac key formats:

**Windows Format Keys**

* Letters: `A`, `B`, `C`, ... `Z`
* Numbers: `Zero`, `One`, `Two`, ... `Nine`
* Modifiers: `Shift`, `LeftCtrl`, `RightCtrl`, `LeftAlt`, `RightAlt`
* Navigation: `Left`, `Right`, `Up`, `Down`, `Home`, `End`, `PageUp`, `PageDown`
* Special: `Space`, `Return`, `Backspace`, `Escape`, `Tab`, `Delete`, etc.
* Symbols: `BackTick`, `BackSlash`, `ForwardSlash`, `Plus`, `Minus`, etc.

**Mac Format Keys**

* Letters: `KeyA`, `KeyB`, `KeyC`, ... `KeyZ`
* Numbers: `Num0`, `Num1`, `Num2`, ... `Num9`
* Modifiers: `ShiftLeft`, `ShiftRight`, `ControlLeft`, `ControlRight`, `Alt`, `AltGr`, etc.
* Navigation: `LeftArrow`, `RightArrow`, `UpArrow`, `DownArrow`
* Function keys: `F1`, `F2`, ... `F12`
* Symbols: `BackQuote`, `Equal`, `Minus`, `LeftBracket`, `RightBracket`, etc.

#### Event Processing

The demonstration system processes these raw events into higher-level actions:

1. **mouseclick**: A brief press and release at nearly the same position
2. **mousedrag**: A sequence of mouse movements with the button held down
3. **type**: A sequence of character inputs combined into text
4. **hotkey**: Special key combinations like keyboard shortcuts

## Tips for Quality Recordings

* **Clear Actions**: Make deliberate, clear mouse movements and clicks
* **Consistent Typing**: Type at a steady pace to ensure accurate capture
* **Complete Workflows**: Ensure you capture all steps without skipping any
* **Minimize Errors**: While the system can handle corrections, try to minimize misclicks or typing errors

### Demonstration Metadata (meta.json)

The `meta.json` file contains important contextual information about each demonstration:

```json
{
  "id": "20250304_151816",                        // Unique identifier for the demonstration (timestamp format)
  "timestamp": "2025-03-04T15:18:16.813394600-05:00", // When the demonstration was recorded (ISO 8601 format)
  "duration_seconds": 21,                         // Total length of the demonstration in seconds
  "status": "completed",                          // Current status of the demonstration (completed, in-progress, aborted)
  "title": "Find Kendrick Lamar concert tickets", // Title of the demonstration task
  "description": "",                              // Optional additional description

  "platform": "windows",                          // Operating system used (windows, macos, linux)
  "arch": "x86_64",                               // System architecture
  "version": "10.0.26100",                        // OS version
  "locale": "en-GB",                              // System language/region setting
  "primary_monitor": {                            // Information about the main display
    "width": 3440,                                // Screen width in pixels
    "height": 1440                                // Screen height in pixels
  },

  "reason": "fail",                               // Why the demonstration ended (fail = task failed, done = task completed)
  "quest": {                                      // Information about the assigned task
    "title": "Find Kendrick Lamar concert tickets", // Task title
    "app": "StubHub",                             // Primary application to be used
    "icon_url": "https://s2.googleusercontent.com/s2/favicons?domain=stubhub.com&sz=64", // Icon for the application
    "objectives": [                               // Step-by-step objectives for the task
      "Open <app>StubHub</app> website in your browser",
      "Search for Kendrick Lamar concert in Inglewood",
      "Select quantity of tickets and apply price filter",
      "Review available options before purchase"
    ],
    "content": "Hi! I need to find 4 tickets to the Kendrick Lamar concert in Inglewood, and I'm trying to keep it under $500. Can you assist me with using StubHub?", // Task instructions in natural language
    "pool_id": "67af7cf3a903635118192a5d",        // Identifier for the task pool
    "reward": {                                   // Reward information
      "time": 1741119480000,                      // Timestamp when reward was calculated
      "max_reward": 7                             // Maximum possible reward for completing this task (in $VIRAL)
    }
  }
}
```

### Video Recording (recording.mp4)

Each demonstration includes a screen recording that shows exactly what the user saw and did during the task. This provides:

1. Visual context for all the recorded interactions
2. Confirmation of the UI state during each action
3. A reference for how the task should be completed
4. Visual verification for quality evaluation

Understanding all components of the demonstration data helps you create high-quality submissions that achieve better scores in the grading system, maximizing both AI training effectiveness and your rewards.
