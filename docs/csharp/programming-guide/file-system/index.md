---
title: Das Dateisystem und die Registrierung – C#-Programmierhandbuch
description: Lesen Sie Artikel zur Verwendung von C# und dem .NET, um verschiedene grundlegende Vorgänge in Dateien, Ordnern und der Registrierung durchzuführen.
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 9e25058f5fb8ae49196c070dd426123e61a55e46
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301631"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="eab81-103">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="eab81-103">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="eab81-104">Die folgenden Artikel zeigen die Verwendung von C# und dem .NET zum Ausführen verschiedener grundlegender Vorgänge in Dateien, Ordnern und der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="eab81-104">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eab81-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eab81-105">In this section</span></span>

|<span data-ttu-id="eab81-106">**Titel**</span><span class="sxs-lookup"><span data-stu-id="eab81-106">**Title**</span></span>|<span data-ttu-id="eab81-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eab81-107">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="eab81-108">Durchlaufen einer Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="eab81-108">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="eab81-109">Zeigt, wie eine Verzeichnisstruktur manuell durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="eab81-109">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="eab81-110">Abrufen von Informationen über Dateien, Ordner und Laufwerke</span><span class="sxs-lookup"><span data-stu-id="eab81-110">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="eab81-111">Zeigt, wie Sie Informationen zu Dateien, Ordnern und Laufwerken abrufen, beispielsweise die Uhrzeit der Erstellung und die Größe.</span><span class="sxs-lookup"><span data-stu-id="eab81-111">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="eab81-112">Erstellen einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="eab81-112">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="eab81-113">Zeigt, wie Sie eine neue Datei oder einen neuen Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="eab81-113">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="eab81-114">Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="eab81-114">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="eab81-115">Zeigt, wie Sie Dateien und Ordner kopieren, löschen und verschieben.</span><span class="sxs-lookup"><span data-stu-id="eab81-115">Shows how to copy, delete and move files and folders.</span></span>|
|[<span data-ttu-id="eab81-116">Bereitstellen eines Statusdialogfelds für Dateioperationen</span><span class="sxs-lookup"><span data-stu-id="eab81-116">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="eab81-117">Zeigt, wie Sie ein standardmäßiges Windows-Fortschrittsdialogfeld für bestimmte Dateivorgänge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eab81-117">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="eab81-118">Schreiben in eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="eab81-118">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="eab81-119">Zeigt, wie Sie in eine Textdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="eab81-119">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="eab81-120">Lesen aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="eab81-120">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="eab81-121">Zeigt, wie Sie aus einer Textdatei lesen.</span><span class="sxs-lookup"><span data-stu-id="eab81-121">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="eab81-122">Zeilenweises Lesen einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="eab81-122">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="eab81-123">Zeigt, wie Sie Text zeilenweise aus einer Datei abrufen.</span><span class="sxs-lookup"><span data-stu-id="eab81-123">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="eab81-124">Erstellen eines Schlüssels in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="eab81-124">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="eab81-125">Zeigt, wie Sie einen Schlüssel in die Systemregistrierung schreiben.</span><span class="sxs-lookup"><span data-stu-id="eab81-125">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="eab81-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="eab81-126">Related sections</span></span>

- [<span data-ttu-id="eab81-127">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="eab81-127">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="eab81-128">Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="eab81-128">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="eab81-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eab81-129">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
