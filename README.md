<h1>chatGPT-shell-cli</h1>

Just simplifed the original script, and make it can remember our conversation.
original repo 0xacx / chatGPT-shell-cli.

## Installation
- Download the `chatgpt_m.sh` file
- Add the OpenAI API key to your shell profile by adding this line `export OPENAI_KEY=your_key_here`
- If you are using iTerm and want to view images in terminal, install [imgcat](https://iterm2.com/utilities/imgcat)

## usage,
./chatgpt_m.sh
alias chatgpt ./chatgpt_m.sh

```shell
$ chatgpt
$ chatgpt -f <your file>
mass of sun
image: cat
history
models / model:
command:
$ echo "How to view running processes on Ubuntu?" | chatgpt
$ chatgpt -p "What is the regex to match an email address?"
```
  - -i, you can set your own initial chat prompt to use in chat context mode. 
  - -f / -ip, You can also set an initial chat prompt from a file with `--init-prompt-from-file` i.e. `chatgpt --init-prompt-from-file myprompt.txt`
  - `image:` To generate images, start a prompt with `image:`
    If you are using iTerm, you can view the image directly in the terminal. Otherwise the script will ask to open the image in your browser.
  - `history` To view your chat history, type `history`
  - `models` To get a list of the models available at OpenAI API, type `models`
  - `model:` To view all the information on a specific model, start a prompt with `model:` and the model `id` as it appears in the list of models. For example: `model:text-babbage:001` will get you all the fields for `text-babbage:001` model
  - `command:` To get a command with the specified functionality and run it, just type `command:` and explain what you want to achieve. The script will always ask you if you want to execute the command. i.e. `command: show me all files in this directory that have more than 150 lines of code` 
  *If a command modifies your file system or dowloads external files the script will show a warning before executing.*
  
## GPT4
  - If you have access to the GPT4 model you can use it by setting the model to `gpt-4`, i.e. `chatgpt --model gpt-4`

## Set request parameters
  - To set request parameters you can start the script like this: `chatgpt --temperature 0.9 --model text-babbage:001 --max-tokens 100 --size 1024x1024`
    The available parameters are: 
      - temperature,  `-t` or `--temperature`
      - model, `-m` or `--model`
      - max number of tokens, `--max-tokens`
      - image size, `-s` or `--size` (The sizes that are accepted by the OpenAI API are 256x256, 512x512, 1024x1024)
      - prompt, `-p` or `--prompt` 
      - prompt from a file in your file system, `-pf or --prompt-from-file`  

## Defaults
- TEMPERATURE = 0.5
- MAX_TOKENS = 1024
- SIZE = 512x512
- CONTEXT = ture
