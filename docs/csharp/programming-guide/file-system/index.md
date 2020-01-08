---
title: Das Dateisystem und die Registrierung – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 3e78d49881a4def5fe9c70ecfe890c8ffee811e8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635300"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="0f364-102">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0f364-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="0f364-103">Die folgenden Themen zeigen die Verwendung von C# und dem .NET Framework zum Ausführen verschiedener grundlegender Vorgänge in Dateien, Ordnern und der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="0f364-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f364-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0f364-104">In This Section</span></span>  
  
|<span data-ttu-id="0f364-105">**Titel**</span><span class="sxs-lookup"><span data-stu-id="0f364-105">**Title**</span></span>|<span data-ttu-id="0f364-106">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0f364-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="0f364-107">Durchlaufen einer Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="0f364-107">How to iterate through a directory tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="0f364-108">Zeigt, wie eine Verzeichnisstruktur manuell durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="0f364-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="0f364-109">Abrufen von Informationen über Dateien, Ordner und Laufwerke</span><span class="sxs-lookup"><span data-stu-id="0f364-109">How to get information about files, folders, and drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="0f364-110">Zeigt, wie Sie Informationen zu Dateien, Ordnern und Laufwerken abrufen, beispielsweise die Uhrzeit der Erstellung und die Größe.</span><span class="sxs-lookup"><span data-stu-id="0f364-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="0f364-111">Erstellen einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="0f364-111">How to create a file or folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="0f364-112">Zeigt, wie Sie eine neue Datei oder einen neuen Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f364-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="0f364-113">Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0f364-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="0f364-114">Zeigt, wie Sie Dateien und Ordner kopieren, löschen und verschieben.</span><span class="sxs-lookup"><span data-stu-id="0f364-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="0f364-115">Bereitstellen eines Statusdialogfelds für Dateioperationen</span><span class="sxs-lookup"><span data-stu-id="0f364-115">How to provide a progress dialog box for file operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="0f364-116">Zeigt, wie Sie ein standardmäßiges Windows-Fortschrittsdialogfeld für bestimmte Dateivorgänge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f364-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="0f364-117">Schreiben in eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="0f364-117">How to write to a text file</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="0f364-118">Zeigt, wie Sie in eine Textdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f364-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="0f364-119">Lesen aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="0f364-119">How to read from a text file</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="0f364-120">Zeigt, wie Sie aus einer Textdatei lesen.</span><span class="sxs-lookup"><span data-stu-id="0f364-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="0f364-121">Zeilenweises Lesen einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="0f364-121">How to read a text file one line at a time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="0f364-122">Zeigt, wie Sie Text zeilenweise aus einer Datei abrufen.</span><span class="sxs-lookup"><span data-stu-id="0f364-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="0f364-123">Erstellen eines Schlüssels in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="0f364-123">How to create a key in the registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="0f364-124">Zeigt, wie Sie einen Schlüssel in die Systemregistrierung schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f364-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="0f364-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0f364-125">Related Sections</span></span>  
 [<span data-ttu-id="0f364-126">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="0f364-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="0f364-127">Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0f364-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)
  
 [<span data-ttu-id="0f364-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0f364-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="0f364-129">Dateien, Ordner und Laufwerke</span><span class="sxs-lookup"><span data-stu-id="0f364-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
