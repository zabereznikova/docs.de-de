---
title: 'Vorgehensweise: Deklarieren einer Konstante'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: 138dd58dac9d1983e35e61f8b98a77810fc6e38b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058845"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Gewusst wie: Deklarieren einer Konstante (Visual Basic)

Verwenden Sie die `Const` -Anweisung, um eine Konstante zu deklarieren und ihren Wert festzulegen. Durch das Deklarieren einer Konstanten weisen Sie einem Wert einen aussagekräftigen Namen zu. Nachdem eine Konstante deklariert wurde, kann Sie nicht geändert werden, oder es kann kein neuer Wert zugewiesen werden.  
  
 Sie deklarieren eine Konstante innerhalb einer Prozedur oder im Deklarations Abschnitt eines Moduls, einer Klasse oder einer Struktur. Konstanten auf Klassen-oder Struktur Ebene sind `Private` standardmäßig, können aber auch als `Public` , `Friend` , `Protected` oder `Protected Friend` für die entsprechende Ebene des Code Zugriffs deklariert werden.  
  
 Die Konstante muss einen gültigen symbolischen Namen aufweisen (die Regeln sind identisch mit denen für das Erstellen von Variablennamen), und ein Ausdruck, der aus numerischen oder Zeichen folgen Konstanten und Operatoren besteht (aber keine Funktionsaufrufe).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>So deklarieren Sie eine Konstante  
  
- Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer, das `Const` Schlüsselwort und einen Ausdruck enthält, wie in den folgenden Beispielen gezeigt:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Wenn die [Option Infer](../../../language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../language-reference/statements/option-strict-statement.md) ist `On` , müssen Sie eine Konstante explizit deklarieren, indem Sie einen-Datentyp angeben ( `Boolean` , `Byte` , `Char` , `DateTime` , `Decimal` , `Double` , `Integer` , `Long` , `Short` , `Single` oder `String` ).  
  
     Wenn auf oder festgelegt ist `Option Infer` `On` `Option Strict` `Off` , können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer- `As` Klausel anzugeben. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Weitere Informationen finden Sie unter [Constant-und literaldatentypen](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>So deklarieren Sie eine Konstante, die über einen explizit angegebenen Datentyp verfügt  
  
- Schreiben Sie eine Deklaration, die das `As` -Schlüsselwort und einen expliziten-Datentyp enthält, wie in den folgenden Beispielen gezeigt:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     Sie können mehrere Konstanten in einer einzelnen Zeile deklarieren, obwohl der Code besser lesbar ist, wenn Sie nur eine einzelne Konstante pro Zeile deklarieren. Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen diese alle die gleiche Zugriffsebene aufweisen ( `Public` ,, `Private` `Friend` , `Protected` oder `Protected Friend` ).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>So deklarieren Sie mehrere Konstanten in einer einzelnen Zeile  
  
- Trennen Sie die Deklarationen durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Const-Anweisung](../../../language-reference/statements/const-statement.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Vorgehensweise: Deklarieren einer Konstante](how-to-declare-a-constant.md)
- [Benutzerdefinierte Konstanten](user-defined-constants.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Vorgehensweise: Gruppieren verwandter konstanter Werte](how-to-group-related-constant-values-together.md)
- [Übersicht über Enumerationen](enumerations-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Vorgehensweise: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)

- [Übersicht über Enumerationen](enumerations-overview.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)
