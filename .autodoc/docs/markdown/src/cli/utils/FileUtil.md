[View code on GitHub](https://github.com/context-labs/autodoc/blob/master/src/cli/utils/FileUtil.ts)

The code in this file provides two functions that are useful for generating URLs for files and folders in a GitHub repository. The first function, `getFileName`, takes an input string and two optional parameters: a delimiter (defaulting to a period) and an extension (defaulting to ".md"). It returns a new string that is the same as the input string, but with the last occurrence of the delimiter replaced by the extension. If the delimiter is not found in the input string, the extension is simply appended to the end of the input string.

For example, if we call `getFileName("README.txt")`, the function will return "README.md". If we call `getFileName("docs/index")`, the function will return "docs/index.md".

The second and third functions, `githubFileUrl` and `githubFolderUrl`, both take three parameters: a GitHub repository root URL, an input root path (which is the local path to the root of the files being processed), and a file or folder path relative to the input root. They both return a URL that points to the corresponding file or folder in the GitHub repository.

For example, if we call `githubFileUrl("https://github.com/user/repo", "/path/to/files", "/path/to/files/docs/index.md")`, the function will return "https://github.com/user/repo/blob/master/docs/index.md". Similarly, if we call `githubFolderUrl("https://github.com/user/repo", "/path/to/files", "/path/to/files/docs")`, the function will return "https://github.com/user/repo/tree/master/docs".

Overall, these functions are useful for generating URLs that can be used to link to files and folders in a GitHub repository from within documentation or other web pages. By using the `getFileName` function to ensure that all file names have the correct extension, and the `githubFileUrl` and `githubFolderUrl` functions to generate the appropriate URLs, developers can easily create links that point to the correct location in the repository.
## Questions: 
 1. What does the `getFileName` function do?
   - The `getFileName` function takes in a string input and optional delimiter and extension parameters, and returns a string with the extension appended to the input string after the last occurrence of the delimiter (if any).
2. What is the purpose of the `githubFileUrl` function?
   - The `githubFileUrl` function takes in a GitHub root URL, an input root path, and a file path, and returns a URL to the file on GitHub by appending the file path to the GitHub root URL and removing the input root path from the beginning of the file path.
3. How does the `githubFolderUrl` function differ from the `githubFileUrl` function?
   - The `githubFolderUrl` function is similar to the `githubFileUrl` function, but takes in a folder path instead of a file path, and returns a URL to the folder on GitHub instead of a URL to a file.