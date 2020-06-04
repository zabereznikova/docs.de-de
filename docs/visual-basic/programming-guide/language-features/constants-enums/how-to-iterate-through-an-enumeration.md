---
title: 'Vorgehensweise: Durchlaufen einer Enumeration'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: fb6fbdd45ca0e84ccb9fc55296d78e3867d5fe25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414426"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Gewusst wie: Durchlaufen einer Enumeration in Visual Basic
Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen. Um eine Enumeration zu durchlaufen, können Sie Sie mithilfe der-Methode in ein Array verschieben <xref:System.Enum.GetValues%2A> . Sie können auch eine Enumeration mithilfe einer-Anweisung durchlaufen, indem Sie die- `For...Each` oder-Methode verwenden, <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> um die Zeichenfolge oder den numerischen Wert zu extrahieren.  
  
### <a name="to-iterate-through-an-enumeration"></a>So durchlaufen Sie eine Enumeration  
  
- Deklarieren Sie ein Array, und konvertieren Sie die Enumeration mit der- <xref:System.Enum.GetValues%2A> Methode, bevor Sie das Array wie jede andere Variable übergeben. Im folgenden Beispiel werden die einzelnen Member der-Enumeration beim <xref:Microsoft.VisualBasic.FirstDayOfWeek> durchlaufen der-Enumeration angezeigt.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Enumerationen](enumerations-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Arrays](../arrays/index.md)
