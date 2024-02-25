# Unity Simple ProgressTracker

## Overview

Unity Simple ProgressTracker is a generic class designed to track progress on a list of items within Unity projects. It provides a flexible way to define execution requirements and actions for each item in the list and automatically updates the progress based on specified conditions.

## Features

- Generic implementation for tracking progress on a list of items.
- Supports customizable execution requirements and actions for each item.
- Designed to be integrated into Unity projects seamlessly.
- Easy-to-use interface for initializing and updating progress.

## Installation

To use the ProgressTracker class in your Unity project, follow these steps:

1. Download or clone the repository.
2. Copy the `ProgressTracker.cs` script into your Unity project's Assets folder.

## Usage

1. Create a list of items you want to track progress on.
2. Define the execution requirements and actions using lambda functions or methods.
3. Initialize the ProgressTracker instance with the list, requirements, and actions.
4. Call the `Update()` method within the `Update()` function of a MonoBehaviour script in Unity to track progress.

Example:

```csharp
using UnityEngine;
using System;
using System.Collections.Generic;

public class Example : MonoBehaviour
{
    private ProgressTracker<int> progressTracker;

    private void Start()
    {
        List<int> itemList = new List<int>() { 1, 2, 3, 4, 5 };
        // Example requirement: Even numbers
        Func<int, bool> requirements = (item) => item % 2 == 0; 
        // Example action: Log item processed
        Action<int> actions = (item) => Debug.Log("Item " + item + " processed."); 

        progressTracker = new ProgressTracker<int>(itemList, requirements, actions);
    }

    private void Update()
    {
        progressTracker.Update();
    }
}
```

## Contributing

Contributions are welcome! Fork the repository, make your changes, and submit a pull request.

If you encounter any issues or have suggestions for improvement, please open an issue.
