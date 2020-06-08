---
title: Dateizugriff
ms.date: 07/20/2015
helpviewer_keywords:
- file access
- files [Visual Basic], input and output
- file access, Visual Basic
- files [Visual Basic], I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files [Visual Basic], accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
ms.openlocfilehash: 3b2042862ae81a52d62374e35a456766ed47edc9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401731"
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="d7894-102">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7894-102">File Access with Visual Basic</span></span>

<span data-ttu-id="d7894-103">Das `My.Computer.FileSystem`-Objekt bietet Tools zum Arbeiten mit Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="d7894-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="d7894-104">Seine Eigenschaften, Methoden und Ereignisse erlauben es Ihnen, Dateien und Ordner zu erstellen, zu kopieren, zu verschieben, zu untersuchen und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d7894-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="d7894-105">`My.Computer.FileSystem` bietet eine bessere Leistung als die von Visual Basic bereitgestellten älteren Funktionen (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` usw.), um Abwärtskompatibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="d7894-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by Visual Basic for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7894-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d7894-106">In This Section</span></span>  

 [<span data-ttu-id="d7894-107">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="d7894-107">Reading from Files</span></span>](reading-from-files.md)  
 <span data-ttu-id="d7894-108">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Lesen aus Dateien auf</span><span class="sxs-lookup"><span data-stu-id="d7894-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="d7894-109">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="d7894-109">Writing to Files</span></span>](writing-to-files.md)  
 <span data-ttu-id="d7894-110">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Schreiben in Dateien auf</span><span class="sxs-lookup"><span data-stu-id="d7894-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="d7894-111">Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="d7894-111">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="d7894-112">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Erstellen, Kopieren, Löschen und Verschieben von Dateien und Ordnern auf.</span><span class="sxs-lookup"><span data-stu-id="d7894-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="d7894-113">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="d7894-113">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="d7894-114">Erläutert, wie `TextFieldReader` verwendet wird, um Textdateien wie z.B. Protokolle zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="d7894-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="d7894-115">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="d7894-115">File Encodings</span></span>](file-encodings.md)  
 <span data-ttu-id="d7894-116">Beschreibt Dateicodierungen und deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d7894-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="d7894-117">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7894-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="d7894-118">Veranschaulicht, wie ein Dienstprogramm erstellt wird, das Informationen zu Dateien und Ordnern meldet.</span><span class="sxs-lookup"><span data-stu-id="d7894-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="d7894-119">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="d7894-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="d7894-120">Listet häufige Probleme beim Lesen und Schreiben in Textdateien auf, und gibt Vorschläge zu entsprechenden Lösungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="d7894-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
