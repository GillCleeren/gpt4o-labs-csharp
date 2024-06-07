# GPT-4o Labs Sample with C#

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](/LICENSE)
[![Twitter: elbruno](https://img.shields.io/twitter/follow/elbruno.svg?style=social)](https://twitter.com/elbruno)
![GitHub: elbruno](https://img.shields.io/github/followers/elbruno?style=social)

Welcome to the GPT-4o Labs samples using C#. This repository contains a demo projects that showcases how to integrate the powerful GPT-4o model with the new OpenAI Library for .NET and Semantic Kernel in a .NET environment.

## Prerequisites

Before running the sample, ensure you have the following installed:
- **.NET 8**: Make sure you have the latest version of .NET installed on your machine.
- **OpenAI Key**: An OpenAI API key is required to authenticate and interact with the GPT-4o model.
- **(Optional) Visual Studio or Visual Studio Code**: You will need an IDE or code editor capable of running .NET projects. Visual Studio or Visual Studio Code are recommended.

## About the Samples

The following samples demonstrates differnet capabilities of the GPT-4o model, in example: analyzing and describing an image. The samples uses the official OpenAI library for .NET and Semantic Kernel to process the image and generate a description using C#.

Here is the list of projects:

| Name | Category | Service | Description | Source |
|------|------|------|-------------|--------|
| GPT4o_lab01 | Semantic Kernel | OpenAI APIs | Chat sample analizing an image from a URL | `.\src\GPT4o_lab01` |
| GPT4o_lab02 | Semantic Kernel | OpenAI APIs | Audio to text sample | `.\src\GPT4o_lab02` |
| GPT4o_lab03 | Semantic Kernel | Azure OpenAI | Chat sample analizing an image from a URL | `.\src\GPT4o_lab03` |
| GPT4o_lab04 | Semantic Kernel | Azure OpenAI | Upload an image to an zure Blob and then analizes the image from the blob URL. *Reference: [.NET and Azure Blobs](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-dotnet?WT.mc_id=academic-00000-brunocapuano)* | `.\src\GPT4o_lab04` |
| OAINETSDK_lab01 | OpenAI library for .NET | OpenAI APIs | Chat sample asking questions to `GPT-4o` | `.\src\OAINETSDK_lab01` |
| OAINETSDK_lab02 | OpenAI library for .NET | OpenAI APIs | Audio to text using `Whisper-1` | `.\src\OAINETSDK_lab02` |
| OAINETSDK_lab03 | OpenAI library for .NET | OpenAI APIs | Chat sample analizing an image from a local file with `GPT-4o` | `.\src\OAINETSDK_lab03` |



## Example: How to Run the Project

To run the project, follow these steps:
1. Clone the repository to your local machine.
1. Open a terminal and enter your OpenAI Key with the following commands 

    ```bash
    cd .\src\GPT4o_lab01\

    # init projecs user-secrets
    dotnet user-secrets init

    # add OpenAI API Key
    dotnet user-secrets set "APIKEY" "OpenAI API KEY"
    ```

1. Run the project with the command

    ```bash
    dotnet run
    ```

1.  The current project analyzes this image

    ![Ultra running mug](/imgs/ultrarunningmug.png)

1. You should see an output similar to this one:

    *The image shows a person holding a mug that has the text "Ultrarunning (verb) the art of running as far as you can, and then running another 20 miles." In the background, there is a scenic view of trees and lush greenery, along with an outdoor swimming pool surrounded by a paved deck with lounge chairs. Additionally, a dog is partially visible near the bottom right of the image, standing near the railing. The scene appears to be tranquil and picturesque, likely taking place in a backyard or a similar outdoor setting.*



## Use another image

In order to test the project with another image, edit the `program.cs` file.

In example, using this new image

![Bruno Standing in a podium](/imgs/rpi5.png)

And updating the code

```csharp
var collectionItems= new ChatMessageContentItemCollection
{
    new TextContent("What's in the image?"),
    new ImageContent(new Uri("https://github.com/elbruno/gpt4ol-sk-csharp/blob/main/imgs/rpi5.png?raw=true"))
};
history.AddUserMessage(collectionItems);
```

We get an output similar to this one:

    The image appears to be a screenshot of a terminal window running on a Raspberry Pi device. The user has executed the `neofetch` command with `sudo`, and the terminal displayed system information. Additionally, the `ollama list` command was executed, showing a list of local models.

    Here's the breakdown of the terminal output:

    ### System Information (Neofetch Output)
    - **OS:** Debian GNU/Linux 12 (bookworm) aarch64
    - **Host:** Raspberry Pi 5 Model B Rev 1.0
    - **Kernel:** 6.6.20+rpt-rpi-2712
    - **Uptime:** 3 mins
    - **Packages:** 694 (dpkg)
    - **Shell:** bash 5.2.15
    - **CPU:** 4 cores @ 2.400GHz
    - **Memory:** 640MiB / 8052MiB

    ### Models List (Ollama List Command Output)
    - **llama3:latest**
    - **ID:** 71a106a91016
    - **Size:** 4.7 GB
    - **Modified:** 4 days ago
    - **phi3:latest**
    - **ID:** a2c89ceaed85
    - **Size:** 2.3 GB
    - **Modified:** 3 days ago


## Author

👤 **Bruno Capuano**

* Website: https://elbruno.com
* Twitter: [@elbruno](https://twitter.com/elbruno)
* Github: [@elbruno](https://github.com/elbruno)
* LinkedIn: [@elbruno](https://linkedin.com/in/elbruno)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

Feel free to check [issues page](https://github.com/elbruno/gpt4ol-sk-csharp//issues).

## Show your support

Give a ⭐️ if this project helped you!


## 📝 License

Copyright &copy; 2024 [Bruno Capuano](https://github.com/elbruno).

This project is [MIT](/LICENSE) licensed.

***
