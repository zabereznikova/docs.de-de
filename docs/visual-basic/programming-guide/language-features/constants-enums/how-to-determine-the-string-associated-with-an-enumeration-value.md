---
title: 'Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c396a4e2ebe973f5be65c3fab5f22cdedb29be1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351130"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)
Die Methoden <xref:System.Enum.GetValues%2A> und <xref:System.Enum.GetNames%2A> ermöglichen es Ihnen, die Zeichen folgen und Werte zu ermitteln, die mit Enumerationsmembern verknüpft sind.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>So bestimmen Sie die Zeichenfolge, die einer Enumeration zugeordnet ist  
  
- Verwenden Sie die <xref:System.Enum.GetNames%2A>-Methode, um die den Enumerationsmembern zugeordneten Zeichen folgen abzurufen. In diesem Beispiel wird eine Enumeration deklariert, `flavorEnum`und dann die <xref:System.Enum.GetNames%2A>-Methode verwendet, um die den einzelnen Membern zugeordneten Zeichen folgen anzuzeigen.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
