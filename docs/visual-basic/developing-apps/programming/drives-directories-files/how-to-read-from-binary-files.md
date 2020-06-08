---
title: 'Gewusst wie: Lesen von Binärdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: 3b4108034b86d99143fff6943e68ca0077ebd21b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359928"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="8e9aa-102">Gewusst wie: Lesen von Binärdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e9aa-102">How to: Read From Binary Files in Visual Basic</span></span>

<span data-ttu-id="8e9aa-103">Das `My.Computer.FileSystem`-Objekt bietet die `ReadAllBytes`-Methode zum Lesen von Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="8e9aa-104">Lesen aus einer Binärdatei</span><span class="sxs-lookup"><span data-stu-id="8e9aa-104">To read from a binary file</span></span>  
  
- <span data-ttu-id="8e9aa-105">Verwenden Sie die `ReadAllBytes`-Methode, die den Inhalt einer Datei als Bytearray zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="8e9aa-106">In diesem Beispiel wird aus der Datei `C:/Documents and Settings/selfportrait.jpg` gelesen.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- <span data-ttu-id="8e9aa-107">Für große Binärdateien können Sie die <xref:System.IO.FileStream.Read%2A>-Methode des <xref:System.IO.FileStream>-Objekts verwenden, um nur für einen bestimmten Zeitraum aus der Datei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-107">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="8e9aa-108">Dann können Sie einschränken, welcher Anteil der Datei für jeden Lesevorgang in den Speicher geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-108">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="8e9aa-109">In folgendem Codebeispiel wird eine Datei kopiert und der Aufrufer kann angeben, wie viel der Datei pro Lesevorgang in den Speicher gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-109">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8e9aa-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8e9aa-110">Robust Programming</span></span>  

 <span data-ttu-id="8e9aa-111">Die folgenden Bedingungen können einen Ausnahmefehler auslösen:</span><span class="sxs-lookup"><span data-stu-id="8e9aa-111">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="8e9aa-112">Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="8e9aa-113">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="8e9aa-114">Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-114">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="8e9aa-115">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-115">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="8e9aa-116">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-116">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="8e9aa-117">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-117">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="8e9aa-118">Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-118">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
- <span data-ttu-id="8e9aa-119">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="8e9aa-120">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="8e9aa-121">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-121">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="8e9aa-122">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-122">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="8e9aa-123">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-123">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9aa-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e9aa-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="8e9aa-125">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="8e9aa-125">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="8e9aa-126">Gewusst wie: Lesen aus Textdateien mit mehreren Formaten</span><span class="sxs-lookup"><span data-stu-id="8e9aa-126">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="8e9aa-127">Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="8e9aa-127">Storing Data to and Reading from the Clipboard</span></span>](../computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
