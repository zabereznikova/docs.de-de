---
title: 'Vorgehensweise: Abrufen von Informationen zu Dateien, Ordnern und Laufwerken (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Informationen zu Dateien, Ordnern und Laufwerken abrufen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 7cbaea4dc5381a2ebeb97ce2797ffe850488e126
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170453"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="a3125-104">Vorgehensweise: Abrufen von Informationen zu Dateien, Ordnern und Laufwerken (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="a3125-104">How to get information about files, folders, and drives  (C# Programming Guide)</span></span>

<span data-ttu-id="a3125-105">Sie können in .NET auf die Dateisysteminformationen mithilfe folgender Klassen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="a3125-105">In .NET, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="a3125-106">Die Klassen <xref:System.IO.FileInfo> und <xref:System.IO.DirectoryInfo> stehen für eine Datei oder ein Verzeichnis, und sie enthalten Eigenschaften, die viele der Dateiattribute offen legen, die vom NTFS-Dateisystem unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a3125-106">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="a3125-107">Sie enthalten zusätzlich Methoden zum Öffnen, Schließen, Bewegen und Löschen von Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="a3125-107">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="a3125-108">Sie können Instanzen dieser Klassen erstellen, indem Sie eine Zeichenfolge in den Konstruktor übergeben, die den Namen der Datei, des Ordners oder des Laufwerks repräsentiert:</span><span class="sxs-lookup"><span data-stu-id="a3125-108">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="a3125-109">Sie können auch die Namen von Dateien, Ordnern oder Laufwerken abrufen, indem Sie Aufrufe auf <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> und <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3125-109">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a3125-110">Die Klassen <xref:System.IO.Directory?displayProperty=nameWithType> und <xref:System.IO.File?displayProperty=nameWithType> bieten statische Methoden zum Abrufen von Informationen über Verzeichnisse und Dateien.</span><span class="sxs-lookup"><span data-stu-id="a3125-110">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3125-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3125-111">Example</span></span>  

 <span data-ttu-id="a3125-112">Das folgende Beispiel veranschaulicht verschiedene Arten des Zugriffs auf Datei- und Ordnerinformationen.</span><span class="sxs-lookup"><span data-stu-id="a3125-112">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a3125-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a3125-113">Robust Programming</span></span>  

 <span data-ttu-id="a3125-114">Beim Verarbeiten von benutzerdefinierten Pfadzeichenfolgen, sollten Sie auch die Ausnahmen für folgende Bedingungen bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="a3125-114">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="a3125-115">Der Dateiname ist falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="a3125-115">The file name is malformed.</span></span> <span data-ttu-id="a3125-116">Er enthält beispielsweise ungültige Zeichen oder besteht nur aus Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a3125-116">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="a3125-117">Der Dateiname ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a3125-117">The file name is null.</span></span>  
  
- <span data-ttu-id="a3125-118">Der Dateiname übersteigt die vom System definierte Maximallänge.</span><span class="sxs-lookup"><span data-stu-id="a3125-118">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="a3125-119">Der Dateiname enthält einen Doppelpunkt (:).</span><span class="sxs-lookup"><span data-stu-id="a3125-119">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="a3125-120">Wenn die Anwendung nicht die notwendigen Leseberechtigungen für die angegebene Datei hat, gibt die `Exists`-Methode `false` zurück, unabhängig davon, ob ein Pfad vorhanden ist; die Methode löst keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a3125-120">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3125-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3125-121">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="a3125-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a3125-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a3125-123">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a3125-123">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
