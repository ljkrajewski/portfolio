# AI Writing Prompt Cookbook
## Table of Contents
1. [Creating a style guide for consistant style](#creating-a-style-guide-for-consistant-style)
2. [Creating character cards for consistant characters](#creating-character-cards-for-consistant-characters)
3. [Writing chapter summaries to maintain a consistant storyline](#writing-chapter-summaries-to-maintain-a-consistant-storyline)
4. [Bringing all of the pieces together](#bringing-all-of-the-pieces-together)

## Creating a style guide for consistant style
_(Based on [How to Create an AI Style Guide: Write With ChatGPT in Your Own Voice](https://fortelabs.com/blog/how-to-create-an-ai-style-guide-write-with-chatgpt-in-your-own-voice/))_
- Start the process with this prompt with the first writing sample attached.
    ```
    You have expertise in linguistics, natural language processing, and prompt engineering.
    
    Your task is to convert the provided text into an elaborate style guide. 
    
    This guide will serve as a blueprint for creating fresh content on a distinct topic while maintaining the original style demonstrated in the text.
    
    Pay special attention to aspects like:
    
    The voice and tone: How formal or casual is the language? Is it authoritative, friendly, neutral, or something else?
    Mood: What emotional atmosphere is created? Does the text seem cheerful, melancholic, mysterious, etc.?
    Sentence structure: Are the sentences simple, compound, complex, or a mixture? How long are they typically?
    Transition style: How does the writer navigate from one idea to another? What types of transition words or phrases are used?
    Rhythm and pacing: Is the writing fast-paced with lots of short sentences, or is it slow and deliberate with longer sentences?
    Signature styles: Are there any recurring phrases or unique punctuation usage that stands out? Any patterns or repetitions?
    I am particularly interested in the stylistic nuances that set this author’s writing apart. 
    
    Identify those elements in the attached writing sample that could serve as indicators of this author’s distinctive writing style.
    ```
- For each subsequent writing sample, attach the sample and use the following prompt:
    ```
    Perform the same evaluation on the attached writing sample by the same author.
    ```
- When done with all of the samples, have the LLM summarize the writing style with this prompt:
    ```
    You have an expertise in linguistics, natural language processing, fiction writing, and prompt engineering. Convert all of the previous analyses of an author’s writing into an elaborate, detailed style guide to be used as a blueprint for creating fresh content on a distinct topic while maintaining the original style demonstrated in the analyzed texts.
    ```
  _Note: If developing a style guide for a non-fiction writer, replace_ ```fiction``` _in the prompt with_ ```non-fiction```. 
- Make the JSON-formatted style guide to be used for future projects.
    ```
    Take this analysis and convert it into a concise yet detailed JSON-formatted style guide to be used with other writing projects.
    ```
- Save the JSON file.

## Creating character cards for consistant characters
- Start the process of making character cards by attaching the first chapter and the sample character card ("sample.json")
    ```
    Review the attached chapter (in markdown) and create character cards for [list of characters]. Use the same JSON schema used in 'sample.json'. Do not add anything that's not in the chapter.
    ```
- For each subsequent chapter, attach the chapter and run the following prompt:
    ```
    Review the attached chapter (in markdown) and update character cards for [list of characters]. Maintain the current JSON schema. Do not add anything that's not in the chapter. Do not remove anything from the current character cards.
    ```
- When making cards for multiple characters, the LLM may append all of the JSON charater definitions into one file. Use the following prompt to split them out.
    ```
    Separate the character cards into a separate artifact for each character.
    ```
- If a JSON definition becomes corrupted, use the following prompt to fix it.
    ```
    Fix the [character] character card to match the schema of the original "sample.json" card.
    ```
- After a few chapters and after the last chapter, use the following prompt to compress the character cards and reduce duplicate information within the card.
    ```
    Review the character cards for [list of characters]. Consolidate each of them without losing vital data. Maintain the same schema of 'sample.json'.
    ```
- Save each JSON file.

## Writing chapter summaries to maintain a consistant storyline
- Use the following prompt to create a summarized storyline (used to preserve story elements throughout subsequent chapters).
    ```
    Review the attached chapter, then use information from the chapter to populate this JSON-based schema.
    {
      "Title": "",
      "Author": "",
      "OverallThemes": [
        ""
      ],
      "OverallTone": "",
      "OverallSetting": "",
      "MainCharacters": [
        {
          "Name": "",
          "Description": ""
        }
      ],
      "Chapters": [
        {
          "ChapterNumber": 1,
          "ChapterTitle": "",
          "Setting": "",
          "MainCharacters": [
            {
              "Name": "",
              "Description": ""
            }
          ],
          "PlotSummary": [
            ""
          ],
          "Themes": [
            ""
          ],
          "Tone": "",
          "KeySymbolisms": [
            {
              "Symbol": "",
              "Meaning": ""
            }
          ],
          "CharacterDevelopment": [
            {
              "Character": "",
              "Development": ""
            }
          ],
          "ConnectionsToPreviousChapters": [
            {
              "Chapter": "",
              "Connection": ""
            }
          ]
        }
      ]
    }
    ```
- For subsequent chapters, use the following prompt to add chapters.
    ```
    Review the attached chapter and append its data as a new chapter to the previous JSON artifact.
    ```
