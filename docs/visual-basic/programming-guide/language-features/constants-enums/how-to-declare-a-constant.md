---
title: 'Gewusst wie: Deklarieren einer Konstante'
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
ms.openlocfilehash: 5054d4a4fc02d8bd22efceb01770fc54167d8cb3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347471"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Gewusst wie: Deklarieren einer Konstante (Visual Basic)
Verwenden Sie die `Const`-Anweisung, um eine Konstante zu deklarieren und ihren Wert festzulegen. Durch das Deklarieren einer Konstanten weisen Sie einem Wert einen aussagekräftigen Namen zu. Nachdem eine Konstante deklariert wurde, kann Sie nicht geändert werden, oder es kann kein neuer Wert zugewiesen werden.  
  
 Sie deklarieren eine Konstante innerhalb einer Prozedur oder im Deklarations Abschnitt eines Moduls, einer Klasse oder einer Struktur. Konstanten auf Klassen-oder Struktur Ebene werden standardmäßig `Private`, können aber auch als `Public`, `Friend`, `Protected`oder `Protected Friend` für die entsprechende Ebene des Code Zugriffs deklariert werden.  
  
 Die Konstante muss einen gültigen symbolischen Namen aufweisen (die Regeln sind identisch mit denen für das Erstellen von Variablennamen), und ein Ausdruck, der aus numerischen oder Zeichen folgen Konstanten und Operatoren besteht (aber keine Funktionsaufrufe).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>So deklarieren Sie eine Konstante  
  
- Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer, das `Const`-Schlüsselwort und einen Ausdruck enthält, wie in den folgenden Beispielen gezeigt:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Wenn die [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`ist, müssen Sie eine Konstante explizit deklarieren, indem Sie einen Datentyp angeben (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`oder `String`).  
  
     Wenn `Option Infer` `On` oder `Option Strict` `Off`ist, können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer `As`-Klausel anzugeben. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Weitere Informationen finden Sie unter [Constant-und literaldatentypen](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>So deklarieren Sie eine Konstante, die über einen explizit angegebenen Datentyp verfügt  
  
- Schreiben Sie eine Deklaration, die das `As`-Schlüsselwort und einen expliziten Datentyp enthält, wie in den folgenden Beispielen gezeigt:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     Sie können mehrere Konstanten in einer einzelnen Zeile deklarieren, obwohl der Code besser lesbar ist, wenn Sie nur eine einzelne Konstante pro Zeile deklarieren. Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen diese alle die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`oder `Protected Friend`) aufweisen.  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>So deklarieren Sie mehrere Konstanten in einer einzelnen Zeile  
  
- Trennen Sie die Deklarationen durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Gewusst wie: Deklarieren einer Konstante](how-to-declare-a-constant.md)
- [Benutzerdefinierte Konstanten](user-defined-constants.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Gewusst wie: Gruppieren verwandter konstanter Werte](how-to-group-related-constant-values-together.md)
- [Übersicht über Enumerationen](enumerations-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md)
- [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)

- [Übersicht über Enumerationen](enumerations-overview.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
