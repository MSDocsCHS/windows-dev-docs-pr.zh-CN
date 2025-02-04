---
title: Quickstart Playground in Dev Home
description: Quickstart playground is an experimental feature in Windows Dev Home that allows you to input a natural language prompt, and then generate a full ready to develop environment with just the click of a button using the power of AI.
ms.date: 05/21/2024
ms.topic: overview
---

# Quickstart Playground in Dev Home

**Quickstart Playground** is an experimental feature in Dev Home, designed to create ready-to-use app development projects through the use of natural language prompts. You can, for example, enter the prompt: “Create a project to develop the game Snake using Python”, select **Generate**, and then open up that project inside of Visual Studio Code. Quickstart Playground in Dev Home streamlines the development process, offering a user-friendly interface for creating starter project templates. 

This feature is powered by the 'Dev containers with OpenAI' extension in Dev Home.

## Pre-requisites

To use this feature, you will need to install: 

- [Docker Desktop]( https://www.docker.com/products/docker-desktop/)
- [Visual Studio Code]( https://code.visualstudio.com/)
- [Visual Studio Code Dev Container Extension]( https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- An OpenAI account with available paid credits

This tool will create a Dev Container, which fully defines a development-ready environment. Learn more: [Dev Containers tutorial (VS Code docs)]( https://code.visualstudio.com/docs/devcontainers/tutorial). 

## Enable the feature

As this feature is currently experimental, you first need to open Dev Home and turn the feature on:

1. Navigate to **Settings -> Experimental Features -> Quickstart Playground** and turn this feature on. When you enable this feature, the **Dev Home Azure Extension** will automatically be installed, since it is an extension that can provide functionality for this feature. 

2. Navigate to the **Machine configuration** page from the main navigation menu, you will see the **Quickstart Playground** option in the menu.

:::image type="content" source="../images/quickstart-machine-config.png" alt-text="Dev Home screenshot of machine config page":::

## Create your first Quickstart Playground project

To create your first Quickstart Playground project:

1. Select the **Dev Container using OpenAI** extension (other extensions are supported as well, but for the purpose of this tutorial, we will use OpenAI).
2. Select Quickstart Playground.
3. Complete the set-up steps. Follow instructions to install any required software and input your OpenAI API key (or any required permissions for other extensions).
4. Once set-up steps are complete, you can select from the example prompts at the top, or input your own.
5. Select **Generate** to create the project and view its output.

:::image type="content" source="../images/quickstart-generate.png" alt-text="Dev Home screenshot of generate page":::

6. Select **Open in VS Code** to open the project in Visual Studio Code. You'll then need to select **Reopen in container** to open the project fully as a Dev Container.

:::image type="content" source="../images/quickstart-vscode.png" alt-text="VS Code screenshot of reopen in container":::

7. Explore and run your code. Check Readme files for additional instructions. 

:::image type="content" source="../images/quickstart-vscode-project.png" alt-text="VS Code screenshot of project":::

## Responsible use of AI

Carefully review the output before opening any project generated by AI. It is possible for AI to make mistakes. See the [OpenAI Privacy Policy]( https://openai.com/policies/privacy-policy) and [OpenAI Terms of Use]( https://openai.com/policies/terms-of-use) for guidance on AI use in the Dev Home Quickstart Playground feature.

> [!NOTE]
> If you use this feature and see an error `API key quota exceeded`, that means you do not have credits in your OpenAI account and would need to purchase them.

## Sending feedback

This is an experimental feature and your feedback can help improve it! Contribute feedback by:

- Use the thumbs up or thumbs down following the **Generate** result, indicating whether the response was useful or incorrect. This will help improve accuracy in the future.
- Open Dev Home and select **Settings -> Feedback**. Provide feedback as bug reports or feature requests.

## Troubleshooting

**How do I remove an incorrect OpenAI API key?**

  - Navigate to the 'Extensions' page in Dev Home. Find the **Dev Home Azure Extension** and select it to open the drop-down menu. Select the arrow beside the 'On' button to access the extension settings page. There you will see a **Clear OpenAI API key** button.
