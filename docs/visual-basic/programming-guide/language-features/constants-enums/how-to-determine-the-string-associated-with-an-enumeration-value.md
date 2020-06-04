---
title: 'Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 525da9206472afefa9f85b49ceee0775cbd168c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414465"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)
Die <xref:System.Enum.GetValues%2A> -Methode und die- <xref:System.Enum.GetNames%2A> Methode ermöglichen es Ihnen, die mit Enumerationsmembern verknüpften Zeichen folgen und Werte  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>So bestimmen Sie die Zeichenfolge, die einer Enumeration zugeordnet ist  
  
- Verwenden Sie die- <xref:System.Enum.GetNames%2A> Methode, um die den Enumerationsmembern zugeordneten Zeichen folgen abzurufen. In diesem Beispiel wird eine Enumeration deklariert, `flavorEnum` und dann wird die-Methode verwendet, <xref:System.Enum.GetNames%2A> um die den einzelnen Membern zugeordneten Zeichen folgen anzuzeigen.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
- [Enum-Anweisung](../../../language-reference/statements/enum-statement.md)
