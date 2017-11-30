---
title: 'Gewusst wie: Durchlaufen einer Enumeration in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Gewusst wie: Durchlaufen einer Enumeration in Visual Basic
Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen. Um eine Enumeration zu durchlaufen, können Sie es in ein Array mit Verschieben der <xref:System.Enum.GetValues%2A> Methode. Durchlaufen Sie können auch eine Enumeration mit einer `For...Each` -Anweisung, mit der <xref:System.Enum.GetNames%2A> oder <xref:System.Enum.GetValues%2A> Methode, um die Zeichenfolge oder einen numerischen Wert zu extrahieren.  
  
### <a name="to-iterate-through-an-enumeration"></a>Zum Durchlaufen einer enumeration  
  
-   Ein Array zu deklarieren und konvertieren Sie die Enumeration mit den <xref:System.Enum.GetValues%2A> Methode vor der Übergabe von Arrays als Sie würde jeder anderen Variablen. Im folgende Beispiel werden die einzelnen Member der Enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> beim Durchlaufen der Enumeration gezeigt.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
