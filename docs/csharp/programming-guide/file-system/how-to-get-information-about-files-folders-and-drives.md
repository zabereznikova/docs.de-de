---
title: 'Vorgehensweise: Abrufen von Informationen über Dateien, Ordner und Laufwerke – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 57c7811246dd1de3f009033403ec269082915c09
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590024"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="8906c-102">Vorgehensweise: Abrufen von Informationen über Dateien, Ordner und Laufwerke (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8906c-102">How to: Get Information About Files, Folders, and Drives  (C# Programming Guide)</span></span>
<span data-ttu-id="8906c-103">Sie können im .NET Framework auf die Dateisysteminformationen mithilfe folgender Klassen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="8906c-103">In the .NET Framework, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="8906c-104">Die Klassen <xref:System.IO.FileInfo> und <xref:System.IO.DirectoryInfo> stehen für eine Datei oder ein Verzeichnis, und sie enthalten Eigenschaften, die viele der Dateiattribute offen legen, die vom NTFS-Dateisystem unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8906c-104">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="8906c-105">Sie enthalten zusätzlich Methoden zum Öffnen, Schließen, Bewegen und Löschen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="8906c-105">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="8906c-106">Sie können Instanzen dieser Klassen erstellen, indem Sie eine Zeichenfolge in den Konstruktor übergeben, die den Namen der Datei, des Ordners oder des Laufwerks repräsentiert:</span><span class="sxs-lookup"><span data-stu-id="8906c-106">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="8906c-107">Sie können auch die Namen von Dateien, Ordnern oder Laufwerken abrufen, indem Sie Aufrufe auf <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> und <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="8906c-107">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="8906c-108">Die Klassen <xref:System.IO.Directory?displayProperty=nameWithType> und <xref:System.IO.File?displayProperty=nameWithType> bieten statische Methoden zum Abrufen von Informationen über Verzeichnisse und Dateien.</span><span class="sxs-lookup"><span data-stu-id="8906c-108">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8906c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8906c-109">Example</span></span>  
 <span data-ttu-id="8906c-110">Das folgende Beispiel veranschaulicht verschiedene Arten des Zugriffs auf Datei- und Ordnerinformationen.</span><span class="sxs-lookup"><span data-stu-id="8906c-110">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8906c-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8906c-111">Robust Programming</span></span>  
 <span data-ttu-id="8906c-112">Beim Verarbeiten von benutzerdefinierten Pfadzeichenfolgen, sollten Sie auch die Ausnahmen für folgende Bedingungen bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="8906c-112">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="8906c-113">Der Dateiname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="8906c-113">The file name is malformed.</span></span> <span data-ttu-id="8906c-114">Er enthält beispielsweise ungültige Zeichen oder besteht nur aus Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="8906c-114">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="8906c-115">Der Dateiname ist NULL.</span><span class="sxs-lookup"><span data-stu-id="8906c-115">The file name is null.</span></span>  
  
- <span data-ttu-id="8906c-116">Der Dateiname übersteigt die vom System definierte Maximallänge.</span><span class="sxs-lookup"><span data-stu-id="8906c-116">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="8906c-117">Der Dateiname enthält einen Doppelpunkt (:).</span><span class="sxs-lookup"><span data-stu-id="8906c-117">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="8906c-118">Wenn die Anwendung nicht die notwendigen Leseberechtigungen für die angegebene Datei hat, gibt die `Exists`-Methode `false` zurück, unabhängig davon, ob ein Pfad vorhanden ist; die Methode löst keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8906c-118">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8906c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8906c-119">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="8906c-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8906c-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8906c-121">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8906c-121">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
