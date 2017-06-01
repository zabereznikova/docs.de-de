---
title: 'Gewusst wie: Erstellen von XML-Dokumentation in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 363a20c0fce05566b61e764d05932a9dfb779f90
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic
Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare in den Code einfügen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Erstellen von XML-Dokumentation für einen Typ oder member  
  
1.  In der **Code-Editor**, positionieren Sie den Cursor in die Zeile über den Typ oder Member, für die Sie Dokumentation erstellen möchten.  
  
2.  Typ `'''` (drei einfache Anführungszeichen).  
  
     Ein XML-Skelett für den Typ oder Member wird hinzugefügt, der **Code-Editor**.  
  
3.  Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.  
  
    > [!NOTE]
    >  Wenn Sie zusätzliche Zeilen innerhalb der XML-Dokumentation Block hinzufügen, muss jede Zeile beginnen Sie mit `'''`.  
  
4.  Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentaren verwendet.  
  
     IntelliSense zeigt den Text aus der \<Zusammenfassung > Tag für den Typ oder Member.  
  
5.  Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
