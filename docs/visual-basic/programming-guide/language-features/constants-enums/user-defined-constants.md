---
title: Benutzerdefinierte Konstanten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e5942d8663a8866b2f9794a86756f2bf25660ba5
ms.lasthandoff: 03/13/2017

---
# <a name="user-defined-constants-visual-basic"></a>Benutzerdefinierte Konstanten (Visual Basic)
Eine Konstante ist ein aussagekräftiger Name, der anstelle einer Zahl oder Zeichenfolge, die nicht geändert werden. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben. Konstanten, die definiert werden, durch die Steuerelemente oder Komponenten, mit denen Sie arbeiten können, oder eigene erstellen. Konstanten, die Sie selbst erstellen, werden als beschrieben *benutzerdefinierte*.  
  
 Deklarieren von Konstanten mit der `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens. Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.  
  
## <a name="const-statement-usage"></a>Const-Anweisung  
 Ein `Const` -Anweisung kann eine mathematische darstellen oder Datum/Uhrzeit Menge:  
  
 [!code-vb[VbEnumsTask&#10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Sie können zudem definieren `String` Konstanten:  
  
 [!code-vb[VbEnumsTask&#13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) ist häufig eine Zahl oder Zeichenfolge, aber auch ein Ausdruck sein, der eine Zahl oder eine Zeichenfolge ergibt (Obwohl dieses Ausdrucks Aufrufe von Funktionen enthalten kann). Sie können sogar Konstanten basierend auf zuvor definierten Konstanten definieren:  
  
 [!code-vb[VbEnumsTask&#15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Bereich der benutzerdefinierte Konstanten  
 Ein `Const` Scope-Anweisung ist eine Variable, die am gleichen Speicherort identisch. Sie können den Bereich in einer der folgenden Methoden angeben:  
  
-   Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie es in dieser Prozedur.  
  
-   Um eine Konstante, die für alle Prozeduren in einer Klasse, jedoch nicht für Code außerhalb des Moduls verfügbar zu erstellen, deklarieren Sie ihn in im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante zu erstellen, die für alle Mitglieder einer Assembly, nicht jedoch für Clients außerhalb der Assembly verfügbar ist, deklarieren Sie sie mithilfe der `Friend` -Schlüsselwort in der Sie im Deklarationsabschnitt der Klasse.  
  
-   Um eine Konstante zur Verfügung, in der gesamten Anwendung zu erstellen, deklarieren Sie sie mithilfe der `Public` -Schlüsselwort in den Deklarationen im Abschnitt der-Klasse.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Deklarieren Sie eine Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Vermeiden von zirkulären Verweisen  
 Da Konstanten mithilfe anderer Konstanten definiert werden können, ist es möglich, versehentlich eine *Zyklus*, oder ein Zirkelbezug zwischen zwei oder mehr Konstanten. Ein Zyklus tritt auf, wenn Sie zwei oder mehr öffentliche Konstanten, die jeweils im Hinblick auf die andere, wie im folgenden Beispiel definiert ist:  
  
 [!code-vb[VbEnumsTask Nr.&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 Tritt ein Zyklus [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generiert einen Compilerfehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Konstanten und Literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
