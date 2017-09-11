---
title: "Gewusst wie: Lesen von Binärdateien in Visual Basic"
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
- binary files, reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method, reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: 16
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
ms.openlocfilehash: f5c0a093073b9a064629ae13a52a2295ad184b81
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="fbf49-102">Gewusst wie: Lesen von Binärdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbf49-102">How to: Read From Binary Files in Visual Basic</span></span>
<span data-ttu-id="fbf49-103">Das `My.Computer.FileSystem`-Objekt bietet die `ReadAllBytes`-Methode zum Lesen von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="fbf49-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="fbf49-104">Lesen aus einer Binärdatei</span><span class="sxs-lookup"><span data-stu-id="fbf49-104">To read from a binary file</span></span>  
  
-   <span data-ttu-id="fbf49-105">Verwenden Sie die `ReadAllBytes`-Methode, die den Inhalt einer Datei als Bytearray zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fbf49-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="fbf49-106">In diesem Beispiel wird aus der Datei `C:/Documents and Settings/selfportrait.jpg` gelesen.</span><span class="sxs-lookup"><span data-stu-id="fbf49-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     <span data-ttu-id="fbf49-107">[!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fbf49-107">[!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]</span></span>  
  
-   <span data-ttu-id="fbf49-108">Für große Binärdateien können Sie die <xref:System.IO.FileStream.Read%2A>-Methode des <xref:System.IO.FileStream>-Objekts verwenden, um nur für einen bestimmten Zeitraum aus der Datei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="fbf49-108">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="fbf49-109">Dann können Sie einschränken, welcher Anteil der Datei für jeden Lesevorgang in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fbf49-109">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="fbf49-110">In folgendem Codebeispiel wird eine Datei kopiert und der Aufrufer kann angeben, wie viel der Datei pro Lesevorgang in den Speicher gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="fbf49-110">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     <span data-ttu-id="fbf49-111">[!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="fbf49-111">[!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fbf49-112">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="fbf49-112">Robust Programming</span></span>  
 <span data-ttu-id="fbf49-113">Die folgenden Bedingungen können eine Ausnahme auslösen:</span><span class="sxs-lookup"><span data-stu-id="fbf49-113">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="fbf49-114">Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="fbf49-115">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="fbf49-116">Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-116">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="fbf49-117">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-117">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="fbf49-118">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="fbf49-119">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="fbf49-120">Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-120">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
-   <span data-ttu-id="fbf49-121">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="fbf49-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="fbf49-122">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="fbf49-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="fbf49-123">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="fbf49-123">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="fbf49-124">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbf49-124">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="fbf49-125">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="fbf49-125">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf49-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbf49-126">See Also</span></span>  
 <span data-ttu-id="fbf49-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A></span><span class="sxs-lookup"><span data-stu-id="fbf49-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A></span></span>   
 <span data-ttu-id="fbf49-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span><span class="sxs-lookup"><span data-stu-id="fbf49-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A></span></span>   
 <span data-ttu-id="fbf49-129">[Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span><span class="sxs-lookup"><span data-stu-id="fbf49-129">[Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span></span>  
 <span data-ttu-id="fbf49-130">[Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="fbf49-130">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 [<span data-ttu-id="fbf49-131">Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="fbf49-131">Storing Data to and Reading from the Clipboard</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)

