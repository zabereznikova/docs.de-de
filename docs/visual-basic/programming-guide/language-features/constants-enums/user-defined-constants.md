---
title: Benutzerdefinierte Konstanten
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 351bdb6963e278341c13e53ef19aea0876010aa9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095641"
---
# <a name="user-defined-constants-visual-basic"></a>Benutzerdefinierte Konstanten (Visual Basic)

Eine Konstante ist ein sinnvoller Name, der den Speicherort einer Zahl oder Zeichenfolge annimmt, der sich nicht ändert. Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben. Sie können Konstanten verwenden, die von den Steuerelementen oder Komponenten definiert werden, mit denen Sie arbeiten, oder Sie können eine eigene erstellen. Die von Ihnen selbst erstellten Konstanten werden als *Benutzer definiert*beschrieben.  
  
 Sie deklarieren eine Konstante mit der- `Const` Anweisung, wobei Sie die gleichen Richtlinien verwenden, die Sie zum Erstellen eines Variablen namens verwenden würden. Wenn `Option Strict` ist `On` , müssen Sie den Konstantentyp explizit deklarieren.  
  
## <a name="const-statement-usage"></a>Verwendung der Konstanten Anweisung  

 Eine- `Const` Anweisung kann eine mathematische oder Datums-/Uhrzeitmenge darstellen:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 Außerdem können Konstanten definiert werden `String` :  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) ist oft eine Zahl oder eine Literalzeichenfolge, es kann sich jedoch auch um einen Ausdruck handeln, der zu einer Zahl oder Zeichenfolge führt (obwohl dieser Ausdruck keine Aufrufe von Funktionen enthalten kann). Sie können auch Konstanten in Bezug auf zuvor definierte Konstanten definieren:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Bereich von benutzerdefinierten Konstanten  

 Der Gültigkeits `Const` Bereich einer Anweisung ist identisch mit der einer Variablen, die am gleichen Speicherort deklariert wurde. Der Bereich kann auf eine der folgenden Arten angegeben werden:  
  
- Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie Sie in dieser Prozedur.  
  
- Um eine Konstante zu erstellen, die für alle Prozeduren in einer Klasse, aber nicht für Code außerhalb dieses Moduls verfügbar ist, deklarieren Sie Sie im Deklarations Abschnitt der Klasse.  
  
- Um eine Konstante zu erstellen, die für alle Member einer Assembly, jedoch nicht für externe Clients der Assembly verfügbar ist, deklarieren Sie Sie mithilfe des- `Friend` Schlüssel Worts im Deklarations Abschnitt der-Klasse.  
  
- Um eine in der gesamten Anwendung verfügbare Konstante zu erstellen, deklarieren Sie Sie mithilfe des- `Public` Schlüssel Worts im Deklarations Abschnitt der-Klasse.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Konstanten](how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Vermeiden von Zirkel verweisen  

 Da Konstanten in Bezug auf andere Konstanten definiert werden können, ist es möglich, versehentlich einen *Cycle*oder Zirkel Verweis zwischen mindestens zwei Konstanten zu erstellen. Ein Durchlauf tritt auf, wenn Sie über zwei oder mehr öffentliche Konstanten verfügen, von denen jede in Bezug auf die andere definiert ist, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 Wenn eine Zyklen auftritt, generiert Visual Basic einen Compilerfehler.  
  
## <a name="see-also"></a>Siehe auch

- [Const-Anweisung](../../../language-reference/statements/const-statement.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](index.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)
- [Übersicht über Enumerationen](enumerations-overview.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
