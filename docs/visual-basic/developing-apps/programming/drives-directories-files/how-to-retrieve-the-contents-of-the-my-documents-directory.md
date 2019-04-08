---
title: 'Vorgehensweise: Abrufen des Inhalts des Verzeichnisses „Eigene Dateien“ in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: fe98d3e92726dc6c4ed576ef989d968852c846d6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821828"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="acbac-102">Vorgehensweise: Abrufen des Inhalts des Verzeichnisses „Eigene Dateien“ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acbac-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="acbac-103">Das <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>-Objekt kann verwendet werden, um aus vielen **All Users**-Verzeichnissen zu lesen, z.B. **Dokumente** oder **Desktop**.</span><span class="sxs-lookup"><span data-stu-id="acbac-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="acbac-104">Lesen aus dem Ordner „Dokumente“</span><span class="sxs-lookup"><span data-stu-id="acbac-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="acbac-105">Verwenden Sie die `ReadAllText`-Methode, um Text aus jeder Datei in einem bestimmten Verzeichnis zu lesen.</span><span class="sxs-lookup"><span data-stu-id="acbac-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="acbac-106">Der folgende Code gibt ein Verzeichnis und eine Datei an und verwendet dann `ReadAllText`, um sie in die Zeichenfolge namens `patients` zu lesen.</span><span class="sxs-lookup"><span data-stu-id="acbac-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="acbac-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acbac-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
