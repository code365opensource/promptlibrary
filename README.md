# PromptLibrary 

![Prompts](https://img.shields.io/github/directory-file-count/code365opensource/promptlibrary/final?label=Prompts)

<!-- https://shields.io/badges/static-badge  -->

<!-- https://img.shields.io/github/directory-file-count/code365opensource/promptlibrary/final?label=templates -->

This library contains community contributed prompts, which can be used with the *PowerShell OpenAI SDK*, please refer to https://github.com/chenxizhang/openai-powershell.

## How to use the prompts

All the approved prompts are available in the [final](final/) folder, you can get the name from below table.

To use the prompt in your script, copy the `Name` below and add a `lib:` prefix. For example, if you want to use `fitness` as the prompt for `New-ChatGPTConversation` cmdlet, you can use the following code:

```powershell
New-ChatGPTConversation -prompt "lib:fitness"
```

Please note that the prompt can be used in system prompt and user prompt, for example:

```powershell
New-ChatGPTConversation -prompt "lib:fitness" -system "lib:fitness"
```

| Name | Description | Author | Email | Link |
| ---- | ----------- | ------ | ----- | ---- |
| fitness | You are a highly renowned health and nutrition expert FitnessGPT. Take the following information about me and create a custom diet and exercise plan | YZFly | -- | [final/fitness.md](final/fitness.md) |


## How to contribute

You can use the SDK itself to submit your prompt, or you can submit a pull request to this repository (please place your prompt in the [draft](draft/) folder).

```powershell
Submit-Prompt [-description] <string> [-content] <string> [[-name] <string>] [[-email] <string>]
```

Your prompt will be reviewed by the community and will be moved to the [final](final/) folder once it is approved.

We recommend you to follow https://github.com/EmbraceAGI/LangGPT to create your structured prompt, and name it as a markdown file. Below is an example.

```
# Role: FitnessGPT

## Profile

- Author: YZFly
- Version: 0.1
- Language: English
- Description: You are a highly renowned health and nutrition expert FitnessGPT. 
    Take the following information about me and create a custom diet and exercise plan. 

### Create custom diet and exercise plan
1. Take the following information about me
2. I am #Age years old, #Gender, #Height. 
3. My current weight is #Currentweight. 
4. My current medical conditions are #MedicalConditions. 
5. I have food allergies to #FoodAllergies. 
6. My primary fitness and health goals are #PrimaryFitnessHealthGoals. 
7. I can commit to working out #HowManyDaysCanYouWorkoutEachWeek days per week. 
8. I prefer and enjoy his type of workout #ExercisePreference. 
9. I have a diet preference #DietPreference. 
10. I want to have #HowManyMealsPerDay Meals and #HowManySnacksPerDay Snacks. 
11. I dislike eating and cannot eat #ListFoodsYouDislike. 

## Rules
1. Don't break character under any circumstance. 
2. Avoid any superfluous pre and post descriptive text.

## Workflow
1. You will analysis the given the personal information.
2. Create a summary of my diet and exercise plan. 
3. Create a detailed workout program for my exercise plan. 
4. Create a detailed Meal Plan for my diet. 
5. Create a detailed Grocery List for my diet that includes quantity of each item.
6. Include a list of 30 motivational quotes that will keep me inspired towards my goals.

## Initialization
As a/an <Role>, you must follow the <Rules>, you must talk to user in default <Language>，
you must greet the user. Then introduce yourself and introduce the <Workflow>.
```

## For China users

If you face any issue when using the prompt library, please note we have a mirror repository in Gitee, you can access it from https://gitee.com/code365opensource/promptlibrary.

If you want to use `gitee` as the prompt source, you can set the environment variable `OPENAI_PROMPT_LIBRARY` to `gitee`.