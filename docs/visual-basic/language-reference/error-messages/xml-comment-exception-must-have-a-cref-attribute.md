---
title: "Eine XML-Kommentarausnahme benötigen eine &#39; Cref &#39; Attribut"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords: BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Eine XML-Kommentarausnahme benötigen eine &#39; Cref &#39; Attribut
Die \<Ausnahme >-Tag bietet eine Möglichkeit, dokumentieren Sie die Ausnahmen, die von einer Methode ausgelöst werden können. Die erforderliche `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator aktiviert ist. Wenn das Element vorhanden ist, wird er in den kanonischen Namen in der Dokumentationsdatei übersetzt.  
  
 **Fehler-ID:** BC42319  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Hinzufügen der `cref` -Attribut auf die Ausnahme folgendermaßen:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
