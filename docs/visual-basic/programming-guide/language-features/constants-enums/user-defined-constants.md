---
title: Benutzerdefinierte Konstanten (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9f4210193aeb386d3a4a76794cc9329cb24b2317
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="user-defined-constants-visual-basic"></a>Benutzerdefinierte Konstanten (Visual Basic)
Eine Konstante ist, einen aussagekräftigen Namen, der anstelle einer Zahl oder eine Zeichenfolge, die nicht geändert wird. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben. Konstanten, die durch die Steuerelemente für die Arbeit mit Komponenten definiert werden können, oder eigene erstellen. Konstanten, die Sie selbst erstellen, werden als beschrieben *benutzerdefinierte*.  
  
 Deklarieren von Konstanten mit der `Const` verwenden Sie dieselben Richtlinien zum Erstellen eines Variablennamens-Anweisung. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
## <a name="const-statement-usage"></a>Const-Anweisung  
 Ein `Const` -Anweisung kann eine mathematische Darstellung oder Datum/Uhrzeit Menge:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Sie können zudem definieren `String` Konstanten:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) häufig eine Zahl oder Zeichenfolgenliteral, sondern kann auch ein Ausdruck, der eine Zahl oder eine Zeichenfolge ausgibt (Obwohl dieses Ausdrucks Aufrufen von Funktionen enthalten kann) sein. Sie können auch Konstanten in Bezug auf die zuvor definierten Konstanten definieren:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Umfang der benutzerdefinierte Konstanten  
 Ein `Const` Scope-Anweisung ist identisch mit der eine Variable deklariert, die am gleichen Speicherort. Sie können den Bereich in einem der folgenden Arten angeben:  
  
-   Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie es während dieser Prozedur aus.  
  
-   Um eine Konstante, die für alle Prozeduren innerhalb einer Klasse, jedoch nicht für Code außerhalb des Moduls verfügbar zu erstellen, deklarieren sie im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante zu erstellen, die auf alle Elemente einer Assembly, nicht jedoch für Clients außerhalb der Assembly verfügbar ist, deklarieren Sie sie mithilfe der `Friend` Schlüsselwort im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante zur Verfügung, in der gesamten Anwendung zu erstellen, deklarieren Sie sie mithilfe der `Public` Schlüsselwort in den Deklarationen im Abschnitt der Klasse.  
  
 Weitere Informationen finden Sie unter [wie: Deklarieren Sie eine Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Zirkelverweise zu vermeiden  
 Da Konstanten im Hinblick auf andere Konstanten definiert werden können, ist es möglich, versehentlich erstellen eine *der Reihe nach*, oder ein Zirkelbezug zwischen zwei oder mehr Konstanten. Ein Zyklus tritt auf, wenn Sie mindestens zwei öffentliche Konstanten, von die jede im Hinblick auf andere, wie im folgenden Beispiel definiert ist:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 Wenn eine Schleife auftritt, generiert Visual Basic einen Compilerfehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
