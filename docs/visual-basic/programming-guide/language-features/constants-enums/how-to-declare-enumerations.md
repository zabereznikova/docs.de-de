---
title: 'Gewusst wie: Deklarieren einer Enumeration (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: e2dbdbbf6bf7fe3e4b71cbe7edc7a19b18f96ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Gewusst wie: Deklarieren einer Enumeration (Visual Basic)
Sie erstellen eine Enumeration mit den `Enum` Anweisung im Deklarationsabschnitt einer Klasse oder das Modul. Eine Enumeration innerhalb einer Methode nicht deklariert werden. Verwenden Sie zum Angeben der entsprechenden Ebene des Zugriffs `Private`, `Protected`, `Friend`, oder `Public`.  
  
 Ein `Enum` Typ hat einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, von denen jedes eine Konstante darstellt. Der Name muss ein gültiger Visual Basic .NET Qualifizierer sein. Der zugrunde liegende Typ muss eines der ganzzahligen Typen sein –`Byte`, `Short`, `Long` oder `Integer`. Standardmäßig ist `Integer` festgelegt. Enumerationen sind immer stark typisiert und sind nicht austauschbar mit Ganzzahltypen.  
  
 Enumerationen können keine Gleitkommawerte haben. Wenn eine Enumeration einen Gleitkommawert mit zugewiesen ist `Option Strict On`, ein Compilerfehler ausgelöst. Wenn `Option Strict` ist `Off`, der Wert wird automatisch konvertiert, um die `Enum` Typ.  
  
 Informationen zu Namen und zum Verwenden der `Imports` -Anweisung Namensqualifikation unnötig, finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Um eine Enumeration zu deklarieren.  
  
1.  Schreiben Sie eine Deklaration, die eine Codezugriffsebene enthält die `Enum` -Schlüsselwort verwenden und einen gültigen Namen ein, wie in den folgenden Beispielen, von denen jede ein anderes deklariert `Enum`.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Definieren Sie Konstanten in der Enumeration. Standardmäßig wird das erste Konstante in einer Enumeration mit initialisiert `0`, und nachfolgende Konstanten mit einem Wert von mehr als die vorherigen Konstante initialisiert werden. Z. B. die folgende Enumeration `Days`, enthält eine Konstante, die mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante, die mit dem Namen `Monday` mit dem Wert `1`, eine Konstante, die mit dem Namen `Tuesday` mit dem Wert des `2`und so weiter.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Sie können Konstanten in einer Enumeration explizit Werte zuweisen, mithilfe einer zuweisungsanweisung. Sie können jeden ganzzahligen Wert, einschließlich negative Zahlen zuweisen. Beispielsweise sollten Sie die Konstanten Werte kleiner als 0 (null), um Fehlerzustände darstellen. In der folgenden Enumeration gilt die Konstante `Invalid` der Wert explizit zugewiesen `–1`, und die Konstante `Sunday` der Wert zugewiesen `0`. Da es das erste Konstante in der Enumeration ist `Saturday` ist auch auf den Wert initialisiert `0`. Den Wert der `Monday` ist `1` (mehr als der Wert der `Sunday`); der Wert der `Tuesday` ist `2`und so weiter.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Um eine Enumeration als einen expliziten Typ zu deklarieren.  
  
-   Geben Sie den Typ der Enumeration mit den `As` -Klausel, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
