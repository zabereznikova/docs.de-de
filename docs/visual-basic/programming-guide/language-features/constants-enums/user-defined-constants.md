---
title: Benutzerdefinierte Konstanten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: dc940105bbeb5e54819b8df5d5b3c831c7a6e145
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527314"
---
# <a name="user-defined-constants-visual-basic"></a>Benutzerdefinierte Konstanten (Visual Basic)
Eine Konstante ist, einen aussagekräftigen Namen, der nimmt den Platz einer Zahl oder Zeichenfolge, die nicht geändert wird. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben. Konstanten, die definiert werden, indem Sie die Steuerelemente oder Komponenten, mit denen Sie zusammenarbeiten können, oder können Sie Ihre eigenen erstellen. Konstanten, die Sie selbst erstellen, werden als beschrieben *benutzerdefinierte*.  
  
 Deklarieren von Konstanten mit dem `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
## <a name="const-statement-usage"></a>Const-Anweisung  
 Ein `Const` -Anweisung kann eine mathematische Darstellung oder Datum/Uhrzeit-Menge:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Sie können auch definieren, `String` Konstanten:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) ist häufig eine Zahl oder Zeichenfolge, es kann aber auch ein Ausdruck, der eine Zahl oder Zeichenfolge führt (Obwohl dieses Ausdrucks Aufrufe von Funktionen enthalten kann). Sie können auch Konstanten in Bezug auf die zuvor definierten Konstanten definieren:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Bereich der benutzerdefinierte Konstanten  
 Ein `Const` Anweisung-Bereich ist identisch mit einer Variablen, die sich am gleichen Standort deklariert. Sie können den Bereich in einem der folgenden Arten angeben:  
  
-   Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie sie während dieser Prozedur aus.  
  
-   Um eine Konstante für alle Prozeduren innerhalb einer Klasse, aber nicht für Code außerhalb des Moduls zu erstellen, deklarieren Sie sie im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante zu erstellen, die auf alle Elemente einer Assembly, aber nicht auf Clients außerhalb der Assembly verfügbar ist, deklarieren Sie sie mithilfe der `Friend` Schlüsselwort im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante, die zur Verfügung, in der gesamten Anwendung zu erstellen, deklarieren Sie sie mithilfe der `Public` Schlüsselwort in den Deklarationen im Abschnitt der-Klasse.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Vermeiden von Zirkelbezügen  
 Da Konstanten im Hinblick auf andere Konstanten definiert werden können, ist es möglich, versehentlich erstellen eine *Zyklus*, oder ein zirkulärer Verweis zwischen zwei oder mehr Konstanten. Ein Zyklus tritt auf, wenn Sie zwei oder mehr öffentliche Konstanten, von die jedes in Bezug auf die andere, wie im folgenden Beispiel definiert ist:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 Wenn eine Schleife auftritt, generiert Visual Basic einen Compilerfehler.  
  
## <a name="see-also"></a>Siehe auch
- [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
