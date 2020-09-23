---
title: 'Vorgehensweise: Verweisen auf einen Enumerationsmember'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095667"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Gewusst wie: Verweisen auf einen Enumerationsmember (Visual Basic)

Enumerationen stellen eine bequeme Möglichkeit zum Arbeiten mit Sätzen verwandter Konstanten und zum Zuordnen konstanter Werte zu Namen dar. Sie können zum Beispiel eine Enumeration für einen Satz von Integerkonstanten deklarieren, denen die Tage der Woche zugewiesen sind, und dann in Ihrem Code die Namen der Wochentage statt deren Integerwerte verwenden.  
  
 Sie können mit der-Anweisung vermeiden, voll qualifizierte Namen zu verwenden `Imports` . Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>So verweisen Sie auf einen Enumerationsmember  
  
- Qualifizieren Sie den Elementnamen mit der-Enumeration. Im folgenden Beispiel wird der-Variablen beispielsweise der- `Saturday` Member der- `FirstDayOfWeek` Enumeration zugewiesen `DayValue` .  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
