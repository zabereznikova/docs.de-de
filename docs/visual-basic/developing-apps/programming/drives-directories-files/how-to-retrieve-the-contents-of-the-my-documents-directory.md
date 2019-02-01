---
title: 'Vorgehensweise: Abrufen des Inhalts des Verzeichnisses „Eigene Dateien“ in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 6313ebd190a6cee8a697399e2e77b63d8c43db2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602584"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Vorgehensweise: Abrufen des Inhalts des Verzeichnisses „Eigene Dateien“ in Visual Basic
Das <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>-Objekt kann verwendet werden, um aus vielen **All Users**-Verzeichnissen zu lesen, z.B. **Dokumente** oder **Desktop**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Lesen aus dem Ordner „Dokumente“  
  
-   Verwenden Sie die `ReadAllText`-Methode, um Text aus jeder Datei in einem bestimmten Verzeichnis zu lesen. Der folgende Code gibt ein Verzeichnis und eine Datei an und verwendet dann `ReadAllText`, um sie in die Zeichenfolge namens `patients` zu lesen.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
