# nc-stack

My agent skills.

## Skills

|       Skill        |                                                                             What it does                                                                                 |
|--------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|`bend-it-like-chach`| Write and refactor React and Next.js interfaces using my preferred style of component composition, explicit types, data-driven rendering, scoped CSS, and semantic HTML. |
|  `passagepin-rag`  |                  Answer questions about a user-selected PDF library using PassagePin. Requirements: PassagePin CLI, Linux x86-64 & glibc 2.38 or newer.                  |

## PassagePin RAG setup

The `passagepin-rag` skill needs PassagePin’s `pdfsearch` executable. Download the Linux x86-64 AppImage from [PassagePin releases](https://github.com/NickChach/passagepin/releases). The current release requires glibc 2.38 or newer.

In a terminal, go to the directory containing the downloaded AppImage and run the following commands. Replace the filename if you downloaded a different version:

```sh
chmod +x PassagePin-1.0.0-x86_64.AppImage
./PassagePin-1.0.0-x86_64.AppImage --appimage-extract 'resources/worker/pdfsearch'
./squashfs-root/resources/worker/pdfsearch --help
```

When invoking the skill, provide the agent with your question and a directory of relevant PDFs. For example:

```text
/passagepin-rag
What does Perry Mehrling say about the role of market makers?
Search ~/Documents/mehrling-books
```

Keep the extracted executable accessible to the agent. The model and runtime are bundled; the executable needs a writable user cache on first use.
