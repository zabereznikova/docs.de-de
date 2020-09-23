---
title: 'Vorgehensweise: Deklarieren einer Enumeration'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 752b425ba32efe41a1ab1aa75de20039d36f5e50
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058897"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Gewusst wie: Deklarieren einer Enumeration (Visual Basic)

Sie erstellen eine Enumeration mit der- `Enum` Anweisung im Deklarations Abschnitt einer Klasse oder eines Moduls. Sie können eine Enumeration nicht innerhalb einer Methode deklarieren. Verwenden Sie,, oder, um die entsprechende Zugriffsebene anzugeben `Private` `Protected` `Friend` `Public` .  
  
 Ein `Enum` Typ verfügt über einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, die jeweils eine Konstante darstellen. Der Name muss ein gültiger Visual Basic .net-Qualifizierer sein. Der zugrunde liegende Typ muss einer der ganzzahligen Typen – `Byte` , `Short` oder sein `Long` `Integer` . Standardmäßig ist `Integer` festgelegt. Enumerationen sind immer stark typisiert und nicht mit ganzzahligen Zahlen Typen austauschbar.  
  
 Enumerationen dürfen keine Gleit Komma Werte aufweisen. Wenn eine Enumeration mit einem Gleit Komma Wert zugewiesen wird `Option Strict On` , führt dies zu einem Compilerfehler. Wenn `Option Strict` `Off` den Wert hat, wird der Wert automatisch in den- `Enum` Typ konvertiert.  
  
 Informationen zu Namen und zum Verwenden der-Anweisung, `Imports` um die namens Qualifizierung unnötig zu machen, finden Sie unter [Enumerationen und namens Qualifizierung](enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>So deklarieren Sie eine Enumeration  
  
1. Schreiben Sie eine Deklaration, die eine Code Zugriffsebene, das `Enum` -Schlüsselwort und einen gültigen Namen enthält, wie in den folgenden Beispielen, von denen jeweils ein anderes deklariert wird `Enum` .  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Definieren Sie die Konstanten in der-Enumeration. Standardmäßig wird die erste Konstante in einer Enumeration mit initialisiert `0` , und nachfolgende Konstanten werden mit einem Wert von einem Wert von einem der vorherigen Konstanten initialisiert. Beispielsweise enthält die folgende Enumeration `Days` eine Konstante `Sunday` mit dem Namen mit dem Wert `0` , eine Konstante `Monday` mit dem Wert `1` , eine Konstante `Tuesday` mit dem Wert `2` und so weiter.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Sie können Konstanten in einer Enumeration mithilfe einer Zuweisungsanweisung explizit Werte zuweisen. Sie können beliebige ganzzahlige Werte zuweisen, einschließlich negativer Zahlen. Beispielsweise möchten Sie, dass Konstanten mit Werten kleiner als 0 (null) Fehlerbedingungen darstellen. In der folgenden Enumeration wird die Konstante `Invalid` explizit dem Wert zugewiesen `–1` , und die Konstante `Sunday` wird dem Wert zugewiesen `0` . Da es sich um die erste Konstante in der-Enumeration handelt, `Saturday` wird auch mit dem-Wert initialisiert `0` . Der Wert von `Monday` ist `1` (ein Wert von ist größer als der Wert von `Sunday` ); der Wert von `Tuesday` ist `2` , usw.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>So deklarieren Sie eine Enumeration als einen expliziten Typ  
  
- Geben Sie den Typ der Aufzählung mit der- `As` Klausel an, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)
