# Batch Subtitle Translator

This Python script allows you to batch translate subtitle files (.srt) from English to Arabic using the Google Translator API. The script supports concurrent processing to speed up the translation of multiple files.

## Prerequisites

Make sure you have Python installed on your machine. You can download it from [python.org](https://www.python.org/downloads/).

## Installation

1. **Clone the repository or download the script:**

   ```sh
   git clone https://github.com/ibrahim-wael-ibrahim/translate_project.git
   ```

2. **Navigate to the project directory:**

   ```sh
   cd batch-subtitle-translator
   ```

3. **Install the required libraries:**

   ```sh
   pip install deep-translator tqdm colorama
   ```

## Usage

1. **Edit the script to specify your input and output directories:**

   Open `batch_translate_subtitles.py` and modify the `input_dir` and `output_dir` variables according to your directory structure. For example:

   ```python
   nameDir = "05 - Developer Skills & Editor Setup"
   input_dir = output_dir = f'/media/ibrahim/FREE SPACE/course/javaScript Course/01.[HowToFree.ORG] Udemy - The Complete JavaScript Course 2023 From Zero to Expert/{nameDir}'
   ```

2. **Run the script:**

   ```sh
   python batch_translate_subtitles.py
   ```

### Script Explanation

- **extract_subtitle_blocks(content):** Splits the subtitle file content into blocks based on double newlines.

- **translate_text(translator, text, src_lang, dest_lang):** Translates the given text from the source language to the target language.

- **translate_subtitle(input_file, output_file, src_lang='en', dest_lang='ar'):** Translates an individual subtitle file and saves the translated content.

- **find_subtitle_files(input_dir, file_extension=".srt"):** Finds all subtitle files with the specified extension in the input directory.

- **translate_file(input_file, output_dir, src_lang, dest_lang):** Translates a single subtitle file and saves it to the output directory.

- **batch_translate_subtitles(input_dir, output_dir, src_lang='en', dest_lang='ar', max_workers=8):** Translates all subtitle files in the input directory concurrently.

### Notes

- The script assumes that your subtitle files are named with the `.en.srt` extension and are located within the specified input directory. The translated files will be saved with the `.ar.srt` extension in the corresponding directory structure.

- If you need to translate subtitles from a different source language or to a different target language, adjust the `src_lang` and `dest_lang` parameters in the script accordingly.

### Customization

If you need to customize the script, you can modify the parameters as needed:

- **src_lang:** Source language code (default is 'en' for English).
- **dest_lang:** Destination language code (default is 'ar' for Arabic).
- **max_workers:** Number of concurrent workers for processing files (default is 8).

For example, to translate from Spanish to French with 4 workers:

```python
batch_translate_subtitles(input_dir, output_dir, src_lang='es', dest_lang='fr', max_workers=4)
```
