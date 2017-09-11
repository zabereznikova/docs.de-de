---
title: LINQ und Dateiverzeichnisse (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9e814c9e9f8519522f288657d6940b07a0b3094
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="d10ba-102">LINQ und Dateiverzeichnisse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="d10ba-103">Viele Dateisystemvorgänge sind im Wesentlichen Abfragen und sind daher für die LINQ-Ansatz gut geeignet.</span><span class="sxs-lookup"><span data-stu-id="d10ba-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="d10ba-104">Beachten Sie, dass die Abfragen in diesem Abschnitt nicht destruktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d10ba-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="d10ba-105">Sie werden nicht verwendet, um den Inhalt der ursprünglichen Dateien oder Ordner ändern.</span><span class="sxs-lookup"><span data-stu-id="d10ba-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="d10ba-106">Dies entspricht die Regel, dass Abfragen keine Nebeneffekte auftreten soll.</span><span class="sxs-lookup"><span data-stu-id="d10ba-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="d10ba-107">Im Allgemeinen sollten Code (einschließlich Abfragen, erstellen, Update- und delete-Operatoren), der Quelldaten modifiziert getrennt vom Code beibehalten werden, die die Daten lediglich Abfragen.</span><span class="sxs-lookup"><span data-stu-id="d10ba-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="d10ba-108">Dieser Abschnitt enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d10ba-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="d10ba-109">Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="d10ba-110">Veranschaulicht, wie zur Suche nach Dateien anhand einer oder mehrerer Eigenschaften seiner <xref:System.IO.FileInfo>Objekt.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="d10ba-111">Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="d10ba-112">Zeigt, wie Gruppen zurückzugeben <xref:System.IO.FileInfo>-Objekt auf Grundlage ihrer Erweiterung.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="d10ba-113">Gewusst wie: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="d10ba-114">Zeigt, wie die Gesamtanzahl der Bytes in allen Dateien in einer angegebenen Verzeichnisstruktur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d10ba-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="d10ba-115">[Gewusst wie: Vergleichen des Inhalts von zwei Ordnern (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="d10ba-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="d10ba-116">Zeigt, wie alle Dateien, die in zwei angegebenen Ordnern vorhanden sind, und auch alle Dateien, die in einem Ordner, aber nicht in der anderen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d10ba-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="d10ba-117">Gewusst wie: Abfragen der größten Datei oder Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="d10ba-118">Zeigt, wie die größten oder kleinsten Datei oder eine angegebene Anzahl von Dateien in einer Verzeichnisstruktur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d10ba-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="d10ba-119">Gewusst wie: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="d10ba-120">Zeigt, wie alle Dateinamen gruppiert, die in mehr als einer Position in einer angegebenen Verzeichnisstruktur auftreten.</span><span class="sxs-lookup"><span data-stu-id="d10ba-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="d10ba-121">Außerdem veranschaulicht, wie komplexere Vergleiche basierend auf einem benutzerdefinierten Vergleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d10ba-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="d10ba-122">Gewusst wie: Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="d10ba-123">Zeigt, wie Ordner in einer Struktur durchlaufen, öffnen jede Datei und Inhalt der Datei abgefragt.</span><span class="sxs-lookup"><span data-stu-id="d10ba-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d10ba-124">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d10ba-124">Comments</span></span>  
 <span data-ttu-id="d10ba-125">Es ist recht aufwändig in Erstellen einer Datenquelle, die genau stellt den Inhalt des Dateisystems und Ausnahmen ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="d10ba-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="d10ba-126">In den Beispielen in diesem Abschnitt erstellen Sie eine Snapshot-Auflistung von <xref:System.IO.FileInfo>-Objekten, die alle Dateien in einem angegebenen Stammordner und allen Unterordnern darstellt.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="d10ba-127">Der aktuelle Status der einzelnen <xref:System.IO.FileInfo>ändert sich die Zeit zwischen den Sie starten und Beenden einer Abfrage möglicherweise.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="d10ba-128">Sie können z. B. eine Liste der erstellen <xref:System.IO.FileInfo>Objekte, die als Datenquelle verwendet.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="d10ba-129">Wenn Sie versuchen, Zugriff auf die `Length` Eigenschaft in einer Abfrage, die <xref:System.IO.FileInfo>Objekt versucht, Zugriff auf das Dateisystem, um den Wert der aktualisieren `Length`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="d10ba-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="d10ba-130">Wenn die Datei nicht mehr vorhanden ist, erhalten Sie eine <xref:System.IO.FileNotFoundException>in einer Abfrage, auch wenn nicht abgefragt werden das Dateisystem direkt.</xref:System.IO.FileNotFoundException></span><span class="sxs-lookup"><span data-stu-id="d10ba-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="d10ba-131">Einige Abfragen in diesem Abschnitt verwenden Sie eine separate Methode, die diese bestimmten Ausnahmen in bestimmten Fällen nutzt.</span><span class="sxs-lookup"><span data-stu-id="d10ba-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="d10ba-132">Eine weitere Option ist die Datenquelle dynamisch aktualisiert werden, mithilfe der <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher> beizubehalten</span><span class="sxs-lookup"><span data-stu-id="d10ba-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10ba-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d10ba-133">See Also</span></span>  
 [<span data-ttu-id="d10ba-134">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10ba-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
