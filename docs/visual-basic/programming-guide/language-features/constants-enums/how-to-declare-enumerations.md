---
title: 'Vorgehensweise: Deklarieren von Enumerationen'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354045"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Gewusst wie: Deklarieren einer Enumeration (Visual Basic)
Sie erstellen eine Enumeration mit der `Enum`-Anweisung im Deklarations Abschnitt einer Klasse oder eines Moduls. Sie können eine Enumeration nicht innerhalb einer Methode deklarieren. Um die entsprechende Zugriffsebene anzugeben, verwenden Sie `Private`, `Protected`, `Friend`oder `Public`.  
  
 Ein `Enum` Typ verfügt über einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, die jeweils eine Konstante darstellen. Der Name muss ein gültiger Visual Basic .net-Qualifizierer sein. Der zugrunde liegende Typ muss einer der ganzzahligen Typen sein –`Byte`, `Short`, `Long` oder `Integer`. `Integer` ist die Standardeinstellung. Enumerationen sind immer stark typisiert und nicht mit ganzzahligen Zahlen Typen austauschbar.  
  
 Enumerationen dürfen keine Gleit Komma Werte aufweisen. Wenn einer Enumeration ein Gleit Komma Wert mit `Option Strict On`zugewiesen wird, führt dies zu einem Compilerfehler. Wenn `Option Strict` `Off`ist, wird der Wert automatisch in den `Enum`-Typ konvertiert.  
  
 Informationen zu Namen und zum Verwenden der `Imports`-Anweisung, um die namens Qualifizierung unnötig zu gestalten, finden Sie unter [Enumerationen und namens Qualifizierung](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>So deklarieren Sie eine Enumeration  
  
1. Schreiben Sie eine Deklaration, die eine Code Zugriffsebene, das `Enum`-Schlüsselwort und einen gültigen Namen enthält, wie in den folgenden Beispielen, von denen jede einen anderen `Enum`deklariert.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Definieren Sie die Konstanten in der-Enumeration. Standardmäßig wird die erste Konstante in einer Enumeration mit `0`initialisiert, und nachfolgende Konstanten werden mit einem Wert von einem Wert von einem der vorherigen Konstanten initialisiert. Beispielsweise enthält die folgende Enumeration, `Days`, eine Konstante mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante mit dem Namen `Monday` mit dem Wert `1`, eine Konstante mit dem Namen `Tuesday` mit dem Wert `2`und so weiter.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Sie können Konstanten in einer Enumeration mithilfe einer Zuweisungsanweisung explizit Werte zuweisen. Sie können beliebige ganzzahlige Werte zuweisen, einschließlich negativer Zahlen. Beispielsweise möchten Sie, dass Konstanten mit Werten kleiner als 0 (null) Fehlerbedingungen darstellen. In der folgenden Enumeration wird dem Konstanten `Invalid` der Wert `–1`explizit zugewiesen, und dem Konstanten `Sunday` wird der Wert `0`zugewiesen. Da es sich um die erste Konstante in der-Enumeration handelt, wird `Saturday` auch mit dem Wert `0`initialisiert. Der Wert von `Monday` ist `1` (ein Wert ist größer als der Wert von `Sunday`). der Wert von `Tuesday` ist `2`, usw.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>So deklarieren Sie eine Enumeration als einen expliziten Typ  
  
- Geben Sie den Typ der Aufzählung mit der `As`-Klausel an, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
