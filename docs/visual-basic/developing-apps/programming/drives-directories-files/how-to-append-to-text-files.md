---
title: 'Vorgehensweise: Anfügen an Textdateien'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
ms.openlocfilehash: 97bcb5c511452e418df010f12d4b63f04251d021
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348871"
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a><span data-ttu-id="dcfaa-102">Vorgehensweise: Anfügen an Textdateien in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcfaa-102">How to: Append to Text Files in Visual Basic</span></span>

<span data-ttu-id="dcfaa-103">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode kann zum Anfügen an eine Textdatei verwendet werden. Dazu müssen Sie den Parameter `append` auf `True` festlegen.</span><span class="sxs-lookup"><span data-stu-id="dcfaa-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to append to a text file by specifying that the `append` parameter is set to `True`.</span></span>  
  
### <a name="to-append-to-a-text-file"></a><span data-ttu-id="dcfaa-104">Anfügen an eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="dcfaa-104">To append to a text file</span></span>  
  
- <span data-ttu-id="dcfaa-105">Verwenden Sie die `WriteAllText`-Methode, geben Sie die Zieldatei und die Zeichenfolge an, die angefügt werden sollen, und legen Sie den `append`-Parameter auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="dcfaa-105">Use the `WriteAllText` method, specifying the target file and string to be appended and setting the `append` parameter to `True`.</span></span>  
  
     <span data-ttu-id="dcfaa-106">Dieses Beispiel schreibt die Zeichenfolge `"This is a test string."` in die Datei namens `Testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="dcfaa-106">This example writes the string `"This is a test string."` to the file named `Testfile.txt`.</span></span>  
  
     [!code-vb[VbFileIOWrite#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="dcfaa-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="dcfaa-107">Robust Programming</span></span>  

 <span data-ttu-id="dcfaa-108">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="dcfaa-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="dcfaa-109">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-109">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="dcfaa-110">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-110">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="dcfaa-111">`File` verweist auf einen Pfad, der nicht vorhanden ist (<xref:System.IO.FileNotFoundException> oder<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-111">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="dcfaa-112">Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-112">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="dcfaa-113">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-113">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="dcfaa-114">Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-114">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="dcfaa-115">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="dcfaa-115">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfaa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcfaa-116">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="dcfaa-117">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="dcfaa-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
