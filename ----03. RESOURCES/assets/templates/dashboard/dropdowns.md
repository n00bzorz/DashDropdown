```dataviewjs
function formatDate(dateString) {
 let date = new Date(dateString);
let options = { year: "2-digit", month: "2-digit", day: "2-digit", hour: "2-digit", minute: "2-digit", hour12: true };
 return date.toLocaleString("en-US", options);
}

let folderTree = new Map();

function addToFolderTree(path, content) {
 let parts = path.split("/");
let currentLevel = folderTree;
  for (let i = 0; i < parts.length; i++) {
    let part = parts[i];
    if (!currentLevel.has(part)) {
      currentLevel.set(part, { folders: new Map(), files: "" });
    }
    if (i === parts.length - 1) {
      currentLevel.get(part).files = content;
    } else {
      currentLevel = currentLevel.get(part).folders;
    }
  }
}

for (let group of dv.pages('"----01. PROJECTS"').groupBy(p => p.file.folder)) {
  let folderName = group.key;
  let rows = group.rows
    .map(
      k => `| [${k.file.name.replace(/\|/g, "\\|")}](/${k.file.path.replace(/ /g, "%20")}) | ${formatDate(k.file.ctime)} | ${formatDate(k.file.mtime)} |`
    )
    .join("\n");
    

let tableContent = `
| Name | Created | Modified |
| ---- | ------- | -------- |
${rows}
\n
`;

  addToFolderTree(folderName, tableContent);
}

function renderFolderTree(folderMap, level = 0) {
  let content = "";
  for (let [folder, data] of folderMap.entries()) {
    let subcontent = data.folders.size > 0 ? renderFolderTree(data.folders, level + 1) : "";
    let folderContent = data.files ? data.files : "";
    if (level > 0) {
      content += `\n<details><summary>${folder}</summary>\n\n${subcontent}${folderContent}\n\n</details>\n`;
    } else {
      content += `${subcontent}${folderContent}`;
    }
  }
  return content;
}

dv.header(6, renderFolderTree(folderTree));
```

^3i98sl


```dataviewjs
function formatDate(dateString) {
 let date = new Date(dateString);
let options = { year: "2-digit", month: "2-digit", day: "2-digit", hour: "2-digit", minute: "2-digit", hour12: true };
 return date.toLocaleString("en-US", options);
}

let folderTree = new Map();

function addToFolderTree(path, content) {
 let parts = path.split("/");
let currentLevel = folderTree;
  for (let i = 0; i < parts.length; i++) {
    let part = parts[i];
    if (!currentLevel.has(part)) {
      currentLevel.set(part, { folders: new Map(), files: "" });
    }
    if (i === parts.length - 1) {
      currentLevel.get(part).files = content;
    } else {
      currentLevel = currentLevel.get(part).folders;
    }
  }
}

for (let group of dv.pages('"----02. AREAS"').groupBy(p => p.file.folder)) {
  let folderName = group.key;
  let rows = group.rows
    .map(
      k => `| [${k.file.name.replace(/\|/g, "\\|")}](/${k.file.path.replace(/ /g, "%20")}) | ${formatDate(k.file.ctime)} | ${formatDate(k.file.mtime)} |`
    )
    .join("\n");

  let tableContent = `
| Name | Created | Modified |
| ---- | ------- | -------- |
${rows}
`;

  addToFolderTree(folderName, tableContent);
}

function renderFolderTree(folderMap, level = 0) {
  let content = "";
  for (let [folder, data] of folderMap.entries()) {
    let subcontent = data.folders.size > 0 ? renderFolderTree(data.folders, level + 1) : "";
    let folderContent = data.files ? data.files : "";
    if (level > 0) {
      content += `\n<details><summary>${folder}</summary>\n\n${subcontent}${folderContent}\n\n</details>\n`;
    } else {
      content += `${subcontent}${folderContent}`;
    }
  }
  return content;
}

dv.header(6, renderFolderTree(folderTree));

```

^5x4i4b



```dataviewjs
function formatDate(dateString) {
 let date = new Date(dateString);
let options = { year: "2-digit", month: "2-digit", day: "2-digit", hour: "2-digit", minute: "2-digit", hour12: true };
 return date.toLocaleString("en-US", options);
}

let folderTree = new Map();

function addToFolderTree(path, content) {
 let parts = path.split("/");
let currentLevel = folderTree;
  for (let i = 0; i < parts.length; i++) {
    let part = parts[i];
    if (!currentLevel.has(part)) {
      currentLevel.set(part, { folders: new Map(), files: "" });
    }
    if (i === parts.length - 1) {
      currentLevel.get(part).files = content;
    } else {
      currentLevel = currentLevel.get(part).folders;
    }
  }
}

for (let group of dv.pages('"----03. RESOURCES"').groupBy(p => p.file.folder)) {
  let folderName = group.key;
  let rows = group.rows
    .map(
      k => `| [${k.file.name.replace(/\|/g, "\\|")}](/${k.file.path.replace(/ /g, "%20")}) | ${formatDate(k.file.ctime)} | ${formatDate(k.file.mtime)} |`
    )
    .join("\n");

  let tableContent = `
| Name | Created | Modified |
| ---- | ------- | -------- |
${rows}
`;

  addToFolderTree(folderName, tableContent);
}

function renderFolderTree(folderMap, level = 0) {
  let content = "";
  for (let [folder, data] of folderMap.entries()) {
    let subcontent = data.folders.size > 0 ? renderFolderTree(data.folders, level + 1) : "";
    let folderContent = data.files ? data.files : "";
    if (level > 0) {
      content += `\n<details><summary>${folder}</summary>\n\n${subcontent}${folderContent}\n\n</details>\n`;
    } else {
      content += `${subcontent}${folderContent}`;
    }
  }
  return content;
}

dv.header(6, renderFolderTree(folderTree));

```

^o23ghr


```dataviewjs
function formatDate(dateString) {
 let date = new Date(dateString);
let options = { year: "2-digit", month: "2-digit", day: "2-digit", hour: "2-digit", minute: "2-digit", hour12: true };
 return date.toLocaleString("en-US", options);
}

let folderTree = new Map();

function addToFolderTree(path, content) {
 let parts = path.split("/");
let currentLevel = folderTree;
  for (let i = 0; i < parts.length; i++) {
    let part = parts[i];
    if (!currentLevel.has(part)) {
      currentLevel.set(part, { folders: new Map(), files: "" });
    }
    if (i === parts.length - 1) {
      currentLevel.get(part).files = content;
    } else {
      currentLevel = currentLevel.get(part).folders;
    }
  }
}

for (let group of dv.pages('"----04. ARCHIVES"').groupBy(p => p.file.folder)) {
  let folderName = group.key;
  let rows = group.rows
    .map(
      k => `| [${k.file.name.replace(/\|/g, "\\|")}](/${k.file.path.replace(/ /g, "%20")}) | ${formatDate(k.file.ctime)} | ${formatDate(k.file.mtime)} |`
    )
    .join("\n");

  let tableContent = `
| Name | Created | Modified |
| ---- | ------- | -------- |
${rows}
`;

  addToFolderTree(folderName, tableContent);
}

function renderFolderTree(folderMap, level = 0) {
  let content = "";
  for (let [folder, data] of folderMap.entries()) {
    let subcontent = data.folders.size > 0 ? renderFolderTree(data.folders, level + 1) : "";
    let folderContent = data.files ? data.files : "";
    if (level > 0) {
      content += `\n<details><summary>${folder}</summary>\n\n${subcontent}${folderContent}\n\n</details>\n`;
    } else {
      content += `${subcontent}${folderContent}`;
    }
  }
  return content;
}

dv.header(6, renderFolderTree(folderTree));

```

^0u2a1t