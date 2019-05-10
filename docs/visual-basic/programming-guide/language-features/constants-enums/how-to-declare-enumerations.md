---
title: 'Vorgehensweise: Deklarieren einer Enumeration (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c74b75adf0f56dd198375cb1ff24656d39ec074c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610580"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Vorgehensweise: Deklarieren einer Enumeration (Visual Basic)
Sie erstellen eine Enumeration mit den `Enum` Anweisung im Abschnitt zu Deklarationen einer Klasse oder das Modul. Sie können eine Enumeration innerhalb einer Methode nicht deklarieren. Verwenden Sie zum Angeben der entsprechenden Zugriffsebene `Private`, `Protected`, `Friend`, oder `Public`.  
  
 Ein `Enum` Typ hat einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, von denen jedes eine Konstante darstellt. Der Name muss ein gültiger Visual Basic .NET Qualifizierer sein. Der zugrunde liegende Typ muss einen ganzzahligen Typ –`Byte`, `Short`, `Long` oder `Integer`. `Integer` Der Standardwert ist. Enumerationen sind immer stark typisiert und sind nicht austauschbar mit Ganzzahltypen.  
  
 Enumerationen dürfen keine Gleitkommawerte haben. Wenn eine Enumeration einen Gleitkommawert mit zugewiesen ist `Option Strict On`, ein Compilerfehler ausgelöst. Wenn `Option Strict` ist `Off`, der Wert wird automatisch konvertiert, um die `Enum` Typ.  
  
 Informationen zu Namen, und wie Sie mit der `Imports` Anweisung, damit Namensqualifikation unnötig, finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Um eine Enumeration zu deklarieren.  
  
1. Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort, und einen gültigen Namen, wie in den folgenden Beispielen wird jeweils ein anderes deklariert `Enum`.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Definieren der Konstanten in der Enumeration. Standardmäßig wird das erste Konstante in einer Enumeration mit initialisiert `0`, und alle nachfolgenden Konstanten werden auf einen Wert von eins mehr als die vorherige Konstante initialisiert. Z. B. die folgende Enumeration `Days`, bietet eine Konstante, die mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante, die mit dem Namen `Monday` mit dem Wert `1`, eine Konstante, die mit dem Namen `Tuesday` mit dem Wert des `2`und so weiter.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Sie können die Konstanten in einer Enumeration mithilfe einer zuweisungsanweisung explizit Werte zuweisen. Sie können einen ganzzahligen Wert, der auch negative Zahlen zuweisen. Beispielsweise sollten Sie die Konstanten Werte, die weniger als 0 (null), um fehlerbedingungen darzustellen. In der folgenden Enumeration, die Konstante `Invalid` wird der Wert explizit zugewiesen `–1`, und die Konstante `Sunday` wird der Wert zugewiesen `0`. Da es sich um das erste Konstante in der Enumeration ist `Saturday` wird auch auf den Wert initialisiert `0`. Der Wert des `Monday` ist `1` (eins mehr als der Wert des `Sunday`); der Wert des `Tuesday` ist `2`und so weiter.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Um eine Enumeration als einen expliziten Typ zu deklarieren.  
  
- Geben Sie den Typ der Enumeration, mit der `As` -Klausel, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
