---
title: 'Gewusst wie: Abrufen des Inhalts des Verzeichnisses "Eigene Dateien" in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3456984a697439a8c2ab7fb88f9f0f32d10cb0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Gewusst wie: Abrufen des Inhalts des Verzeichnisses "Eigene Dateien" in Visual Basic
Das <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>-Objekt kann verwendet werden, um aus vielen **All Users**-Verzeichnissen zu lesen, z.B. **Dokumente** oder **Desktop**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Lesen aus dem Ordner „Dokumente“  
  
-   Verwenden Sie die `ReadAllText`-Methode, um Text aus jeder Datei in einem bestimmten Verzeichnis zu lesen. Der folgende Code gibt ein Verzeichnis und eine Datei an und verwendet dann `ReadAllText`, um sie in die Zeichenfolge namens `patients` zu lesen.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
