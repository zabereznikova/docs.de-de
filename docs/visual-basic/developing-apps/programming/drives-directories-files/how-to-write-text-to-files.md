---
title: 'Gewusst wie: Schreiben von Text in Dateien'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: f95a0c4df4a2eab0069a6dab0d4c3fa338d1d8ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411537"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="596c2-102">Gewusst wie: Schreiben von Text in Dateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="596c2-102">How to: Write Text to Files in Visual Basic</span></span>

<span data-ttu-id="596c2-103">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode kann zum Schreiben von Text in Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="596c2-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="596c2-104">Ist die angegebene Datei noch nicht vorhanden, wird diese erstellt.</span><span class="sxs-lookup"><span data-stu-id="596c2-104">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="596c2-105">Prozedur</span><span class="sxs-lookup"><span data-stu-id="596c2-105">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="596c2-106">Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="596c2-106">To write text to a file</span></span>  
  
- <span data-ttu-id="596c2-107">Verwenden Sie die `WriteAllText`-Methode, um Text in eine Datei zu schreiben, und geben Sie die Datei und den zu schreibenden Text an.</span><span class="sxs-lookup"><span data-stu-id="596c2-107">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="596c2-108">In diesem Beispiel wird der Satz `"This is new text."` in die Datei `test.txt` geschrieben und an jeden vorhandenen Text in der Datei angefügt.</span><span class="sxs-lookup"><span data-stu-id="596c2-108">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     [!code-vb[VbFileIOWrite#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#3)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="596c2-109">Schreiben von mehreren Zeichenfolgen in eine Datei</span><span class="sxs-lookup"><span data-stu-id="596c2-109">To write a series of strings to a file</span></span>  
  
- <span data-ttu-id="596c2-110">Durchlaufen Sie die Zeichenfolgenauflistung.</span><span class="sxs-lookup"><span data-stu-id="596c2-110">Loop through the string collection.</span></span> <span data-ttu-id="596c2-111">Verwenden Sie die `WriteAllText`-Methode, um Text in eine Datei zu schreiben, und geben Sie die Zieldatei und die Zeichenfolge an, die angefügt werden soll, und legen Sie den `append`-Parameter auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="596c2-111">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="596c2-112">In diesem Beispiel werden die Namen der Dateien im `Documents and Settings`-Verzeichnis in `FileList.txt` geschrieben, und es wird ein Wagenrücklauf zur besseren Lesbarkeit eingefügt.</span><span class="sxs-lookup"><span data-stu-id="596c2-112">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     [!code-vb[VbFileIOWrite#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#4)]  
  
## <a name="robust-programming"></a><span data-ttu-id="596c2-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="596c2-113">Robust Programming</span></span>  

 <span data-ttu-id="596c2-114">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="596c2-114">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="596c2-115">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="596c2-116">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="596c2-117">`File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-117">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="596c2-118">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-118">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="596c2-119">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="596c2-120">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="596c2-121">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="596c2-122">Auf dem Datenträger steht kein Platz mehr zur Verfügung, und der Aufruf von `WriteAllText` schlägt fehl (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="596c2-122">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="596c2-123">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="596c2-123">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="596c2-124">Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="596c2-124">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596c2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="596c2-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [<span data-ttu-id="596c2-126">Vorgehensweise: Lesen aus Textdateien</span><span class="sxs-lookup"><span data-stu-id="596c2-126">How to: Read from Text Files</span></span>](how-to-read-from-text-files.md)
