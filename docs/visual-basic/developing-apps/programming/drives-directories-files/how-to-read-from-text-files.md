---
title: 'Vorgehensweise: Lesen aus Textdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 8af088ad269cc77bc5c83aedb86bde9af2e37a15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334591"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="b28da-102">Vorgehensweise: Lesen von Textdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b28da-102">How to: Read From Text Files in Visual Basic</span></span>

<span data-ttu-id="b28da-103">Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A>-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Lesen aus einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="b28da-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="b28da-104">Die Dateicodierung kann angegeben werden, wenn beim Inhalt der Datei eine Codierung wie ASCII oder UTF-8 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b28da-104">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>

<span data-ttu-id="b28da-105">Wenn Sie aus einer Datei mit erweiterten Zeichen lesen, müssen Sie die Dateicodierung angeben.</span><span class="sxs-lookup"><span data-stu-id="b28da-105">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>

> [!NOTE]
> <span data-ttu-id="b28da-106">Um in einer Datei jeweils eine einzelne Textzeile zu lesen, verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A>-Methode des `My.Computer.FileSystem`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b28da-106">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="b28da-107">Die `OpenTextFileReader`-Methode gibt ein <xref:System.IO.StreamReader>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b28da-107">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="b28da-108">Mithilfe der <xref:System.IO.StreamReader.ReadLine%2A>-Methode des `StreamReader`-Objekts kann jeweils eine Zeile in einer Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="b28da-108">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="b28da-109">Sie können mit der <xref:System.IO.StreamReader.EndOfStream%2A>-Methode des `StreamReader`-Objekts einen Test für das Ende der Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="b28da-109">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>

## <a name="to-read-from-a-text-file"></a><span data-ttu-id="b28da-110">So lesen Sie eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="b28da-110">To read from a text file</span></span>

<span data-ttu-id="b28da-111">Verwenden Sie die `ReadAllText`-Methode des `My.Computer.FileSystem`-Objekts, um unter Angabe des Pfads den Inhalt einer Textdatei in eine Zeichenfolge zu lesen.</span><span class="sxs-lookup"><span data-stu-id="b28da-111">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="b28da-112">Im folgenden Beispiel wird der Inhalt von test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b28da-112">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="b28da-113">So lesen Sie aus einer codierten Textdatei</span><span class="sxs-lookup"><span data-stu-id="b28da-113">To read from a text file that is encoded</span></span>

<span data-ttu-id="b28da-114">Verwenden Sie die `ReadAllText`-Methode des `My.Computer.FileSystem`-Objekts, um unter Angabe des Pfads und der Dateicodierung den Inhalt einer Textdatei in eine Zeichenfolge zu lesen.</span><span class="sxs-lookup"><span data-stu-id="b28da-114">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="b28da-115">Im folgenden Beispiel wird der Inhalt der UTF32-Datei test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b28da-115">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a><span data-ttu-id="b28da-116">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b28da-116">Robust Programming</span></span>

<span data-ttu-id="b28da-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b28da-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="b28da-118">Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-118">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="b28da-119">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-119">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="b28da-120">Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-120">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>

- <span data-ttu-id="b28da-121">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-121">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="b28da-122">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="b28da-123">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-123">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="b28da-124">Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-124">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>

- <span data-ttu-id="b28da-125">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b28da-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

<span data-ttu-id="b28da-126">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="b28da-126">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b28da-127">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="b28da-127">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>

<span data-ttu-id="b28da-128">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b28da-128">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="b28da-129">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="b28da-129">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

## <a name="see-also"></a><span data-ttu-id="b28da-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b28da-130">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [<span data-ttu-id="b28da-131">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="b28da-131">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="b28da-132">How to: Lesen aus durch Trennzeichen getrennten Textdateien</span><span class="sxs-lookup"><span data-stu-id="b28da-132">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="b28da-133">How to: Lesen aus einer Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="b28da-133">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="b28da-134">How to: Lesen aus Textdateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="b28da-134">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="b28da-135">Problembehandlung: Lesen aus und Schreiben in Textdateien</span><span class="sxs-lookup"><span data-stu-id="b28da-135">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="b28da-136">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b28da-136">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="b28da-137">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="b28da-137">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
