---
title: 'Gewusst wie: Abrufen des Inhalts des Verzeichnisses "Eigene Dateien"'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: cf4470020507c581999b9d72602ddb6e3e76ed74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334532"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="91e41-102">Gewusst wie: Abrufen des Inhalts des Verzeichnisses "Eigene Dateien" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91e41-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="91e41-103">Das <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>-Objekt kann verwendet werden, um aus vielen **All Users**-Verzeichnissen zu lesen, z.B. **Dokumente** oder **Desktop**.</span><span class="sxs-lookup"><span data-stu-id="91e41-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="91e41-104">Lesen aus dem Ordner „Dokumente“</span><span class="sxs-lookup"><span data-stu-id="91e41-104">To read from the My Documents folder</span></span>  
  
- <span data-ttu-id="91e41-105">Verwenden Sie die `ReadAllText`-Methode, um Text aus jeder Datei in einem bestimmten Verzeichnis zu lesen.</span><span class="sxs-lookup"><span data-stu-id="91e41-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="91e41-106">Der folgende Code gibt ein Verzeichnis und eine Datei an und verwendet dann `ReadAllText`, um sie in die Zeichenfolge namens `patients` zu lesen.</span><span class="sxs-lookup"><span data-stu-id="91e41-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="91e41-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91e41-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
