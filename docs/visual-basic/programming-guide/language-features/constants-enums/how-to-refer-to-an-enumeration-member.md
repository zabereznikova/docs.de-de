---
title: 'Gewusst wie: Verweisen auf einen Enumerationsmember'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 01db5b84783eda45cd7867dc8fea8a69fc18b98a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353997"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Gewusst wie: Verweisen auf einen Enumerationsmember (Visual Basic)
Enumerationen stellen eine bequeme Möglichkeit zum Arbeiten mit Sätzen verwandter Konstanten und zum Zuordnen konstanter Werte zu Namen dar. Sie können zum Beispiel eine Enumeration für einen Satz von Integerkonstanten deklarieren, denen die Tage der Woche zugewiesen sind, und dann in Ihrem Code die Namen der Wochentage statt deren Integerwerte verwenden.  
  
 Sie können mit der `Imports`-Anweisung vermeiden, voll qualifizierte Namen zu verwenden. Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>So verweisen Sie auf einen Enumerationsmember  
  
- Qualifizieren Sie den Elementnamen mit der-Enumeration. Im folgenden Beispiel wird das `Saturday`-Member der `FirstDayOfWeek`-Enumeration der Variablen `DayValue`zugewiesen.  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
