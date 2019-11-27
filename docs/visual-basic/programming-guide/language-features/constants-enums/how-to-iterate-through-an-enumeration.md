---
title: 'Gewusst wie: Durchlaufen einer Enumeration'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354023"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Gewusst wie: Durchlaufen einer Enumeration in Visual Basic
Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen. Um eine Enumeration zu durchlaufen, können Sie Sie mithilfe der <xref:System.Enum.GetValues%2A>-Methode in ein Array verschieben. Sie können auch eine Enumeration mithilfe einer `For...Each`-Anweisung durchlaufen, indem Sie die <xref:System.Enum.GetNames%2A>-oder <xref:System.Enum.GetValues%2A>-Methode verwenden, um die Zeichenfolge oder den numerischen Wert zu extrahieren.  
  
### <a name="to-iterate-through-an-enumeration"></a>So durchlaufen Sie eine Enumeration  
  
- Deklarieren Sie ein Array, und konvertieren Sie die Enumeration mit der <xref:System.Enum.GetValues%2A>-Methode, bevor Sie das Array wie jede andere Variable übergeben. Im folgenden Beispiel werden die einzelnen Member der-Enumeration beim Durchlaufen der-Enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> angezeigt.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
