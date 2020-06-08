---
title: 'Gewusst wie: Analysieren von Dateipfaden'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: eb7714a8594c0bce344eb2e48ebc5053dc3bfbb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359941"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="15f5c-102">Gewusst wie: Analysieren von Dateipfaden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15f5c-102">How to: Parse File Paths in Visual Basic</span></span>

<span data-ttu-id="15f5c-103">Das <xref:Microsoft.VisualBasic.FileIO.FileSystem> -Objekt bietet eine Reihe nützlicher Methoden für die Analyse von Dateipfaden.</span><span class="sxs-lookup"><span data-stu-id="15f5c-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="15f5c-104">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> -Methode übernimmt zwei Pfade und gibt einen korrekt formatierten kombinierten Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="15f5c-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="15f5c-105">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> -Methode gibt den absoluten übergeordneten Pfad des bereitgestellten Pfads zurück.</span><span class="sxs-lookup"><span data-stu-id="15f5c-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="15f5c-106">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> -Methode gibt ein <xref:System.IO.FileInfo> -Objekt zurück, das abgefragt werden kann, um die Eigenschaften der Datei zu ermitteln, beispielsweise deren Name und Pfad.</span><span class="sxs-lookup"><span data-stu-id="15f5c-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="15f5c-107">Beurteilen Sie den Inhalt der Datei nicht anhand der Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="15f5c-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="15f5c-108">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="15f5c-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="15f5c-109">So ermitteln Sie den Namen und den Pfad einer Datei</span><span class="sxs-lookup"><span data-stu-id="15f5c-109">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="15f5c-110">Verwenden Sie die <xref:System.IO.FileInfo.DirectoryName%2A> - und die <xref:System.IO.FileInfo.Name%2A> -Eigenschaft des <xref:System.IO.FileInfo> -Objekts, um den Namen und den Pfad einer Datei zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="15f5c-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="15f5c-111">In diesem Beispiel werden der Name und der Pfad ermittelt und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15f5c-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="15f5c-112">So kombinieren Sie den Namen und das Verzeichnis einer Datei, um den vollständigen Pfad zu erstellen</span><span class="sxs-lookup"><span data-stu-id="15f5c-112">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="15f5c-113">Verwenden Sie die `CombinePath` -Methode, und geben Sie das Verzeichnis und den Namen an.</span><span class="sxs-lookup"><span data-stu-id="15f5c-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="15f5c-114">In diesem Beispiel werden die im vorherigen Beispiel erstellten Zeichenfolgen `folderPath` und `fileName` kombiniert, und das Ergebnis wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15f5c-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="15f5c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15f5c-115">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="15f5c-116">Gewusst wie: Abrufen einer Sammlung von Dateien in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="15f5c-116">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
