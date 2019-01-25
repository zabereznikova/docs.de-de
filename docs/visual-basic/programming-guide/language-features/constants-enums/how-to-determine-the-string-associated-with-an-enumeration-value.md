---
title: 'Vorgehensweise: Bestimmen der Zeichenfolge, die eine Enumerationswert (Visual Basic) zugeordnet sind'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690188"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Vorgehensweise: Bestimmen der Zeichenfolge, die eine Enumerationswert (Visual Basic) zugeordnet sind
Die <xref:System.Enum.GetValues%2A> und <xref:System.Enum.GetNames%2A> Methoden ermöglichen es Ihnen, um zu bestimmen, die Zeichenfolgen und Enumerationsmember zugeordnete Werte.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Um zu bestimmen, die eine Enumeration zugeordnete Zeichenfolge  
  
-   Verwenden der <xref:System.Enum.GetNames%2A> Methode, um die Member der Enumeration zugeordneten Zeichenfolgen abzurufen. Das folgende Beispiel deklariert eine Enumeration, `flavorEnum`, verwendet dann die <xref:System.Enum.GetNames%2A> Methode zum Anzeigen der Zeichenfolgen, die jedes Element zugeordnet.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
