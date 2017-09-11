---
title: Dateizugriff mit Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file access
- files, input and output
- file access, Visual Basic
- files, I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files, accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71e941bf33c3b1051c22c8170b327df9fae7d4b9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="d1af4-102">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1af4-102">File Access with Visual Basic</span></span>
<span data-ttu-id="d1af4-103">Das `My.Computer.FileSystem`-Objekt bietet Tools zum Arbeiten mit Dateien und Ordnern.</span><span class="sxs-lookup"><span data-stu-id="d1af4-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="d1af4-104">Seine Eigenschaften, Methoden und Ereignisse erlauben es Ihnen, Dateien und Ordner zu erstellen, zu kopieren, zu verschieben, zu untersuchen und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d1af4-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="d1af4-105">`My.Computer.FileSystem` bietet eine bessere Leistung als die älteren Funktionen (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` usw.), die von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bereitgestellt werden, um Abwärtskompatibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="d1af4-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1af4-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d1af4-106">In This Section</span></span>  
 [<span data-ttu-id="d1af4-107">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="d1af4-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="d1af4-108">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Lesen aus Dateien auf</span><span class="sxs-lookup"><span data-stu-id="d1af4-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="d1af4-109">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="d1af4-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="d1af4-110">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Schreiben in Dateien auf</span><span class="sxs-lookup"><span data-stu-id="d1af4-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="d1af4-111">Erstellen, Löschen und Verschieben von Dateien und Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="d1af4-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="d1af4-112">Listet Themen im Zusammenhang mit der Verwendung des `My.Computer.FileSystem`-Objekts zum Erstellen, Kopieren, Löschen und Verschieben von Dateien und Ordnern auf.</span><span class="sxs-lookup"><span data-stu-id="d1af4-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="d1af4-113">Analysieren von Textdateien mit dem TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="d1af4-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="d1af4-114">Erläutert, wie `TextFieldReader` verwendet wird, um Textdateien wie z.B. Protokolle zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="d1af4-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="d1af4-115">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="d1af4-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="d1af4-116">Beschreibt Dateicodierungen und deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d1af4-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="d1af4-117">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1af4-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="d1af4-118">Veranschaulicht, wie ein Dienstprogramm erstellt wird, das Informationen zu Dateien und Ordnern meldet.</span><span class="sxs-lookup"><span data-stu-id="d1af4-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="d1af4-119">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="d1af4-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="d1af4-120">Listet häufige Probleme beim Lesen und Schreiben in Textdateien auf, und gibt Vorschläge zu entsprechenden Lösungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="d1af4-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>

