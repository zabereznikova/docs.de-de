---
title: 'Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 63597145e96b04affc5f0e80e05a56b3fdf27278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833359"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic
Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen. Um eine Enumeration zu durchlaufen, können Sie es in ein Array mit Verschieben der <xref:System.Enum.GetValues%2A> Methode. Durchlaufen Sie könnte auch eine Enumeration mit einer `For...Each` -Anweisung, mit der <xref:System.Enum.GetNames%2A> oder <xref:System.Enum.GetValues%2A> Methode, um die Zeichenfolge oder einen numerischen Wert zu extrahieren.  
  
### <a name="to-iterate-through-an-enumeration"></a>Zum Durchlaufen einer enumeration  
  
-   Ein Array zu deklarieren, und konvertieren Sie die Enumeration mit den <xref:System.Enum.GetValues%2A> Methode vor der Übergabe von Arrays wie würden Sie jede andere Variable. Im folgende Beispiel werden die einzelnen Member der Enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> beim Durchlaufen der Enumeration gezeigt.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
