---
title: 'Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c14ea61feba7d7d85f9a4fc377aefdd8fa240c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651699"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Gewusst wie: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge (Visual Basic)
Die <xref:System.Enum.GetValues%2A> und <xref:System.Enum.GetNames%2A> Methoden ermöglichen es Ihnen, um zu bestimmen, die Zeichenfolgen und Werte, die Enumerationsmember zugeordnet.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Um zu bestimmen, die eine Enumeration zugeordnete Zeichenfolge  
  
-   Verwenden der <xref:System.Enum.GetNames%2A> Methode, um die Zeichenfolgen der Enumerationsmember zugeordnete abzurufen. Dieses Beispiel deklariert eine Enumeration `flavorEnum`, dann verwendet der <xref:System.Enum.GetNames%2A> Methode zum Anzeigen der Zeichenfolgen, die jedes Element zugeordnet sind.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
