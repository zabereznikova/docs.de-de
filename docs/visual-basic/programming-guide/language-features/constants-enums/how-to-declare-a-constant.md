---
title: 'Vorgehensweise: Deklarieren einer Konstante (Visual Basic)'
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
ms.openlocfilehash: 95bfa3da5499c518dad0c235b539784fee2bb522
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843408"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Vorgehensweise: Deklarieren einer Konstante (Visual Basic)
Sie verwenden die `Const` Anweisung, um eine Konstante deklariert, und legen Sie dessen Wert. Durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen auf einen Wert an. Nachdem eine Konstante deklariert wird, nicht geändert oder einen neuer Wert zugewiesen.  
  
 Deklarieren von Konstanten in einer Prozedur oder im Deklarationsabschnitt der Module, Klasse oder Struktur. Klasse oder Struktur auf Konstanten sind `Private` standardmäßig aber auch als deklariert werden, kann `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene Code.  
  
 Die Konstante benötigen einen gültigen symbolischen Namen (die Regeln sind identisch mit denen zum Erstellen von Namen von variabler) und einen Ausdruck aus der numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Um eine Konstante zu deklarieren.  
  
-   Schreiben Sie eine Deklaration, Zugriffsspezifizierer hat, enthält, die `Const` -Schlüsselwort und in einem Ausdruck, wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, Sie müssen eine Konstante explizit deklarieren, indem Sie einen Datentyp angeben (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).  
  
     Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Deklarieren einer Konstante können Sie ohne Angabe von einem Datentyp mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Um eine Konstante zu deklarieren, die einen explizit angegebenen Datentyp verfügt  
  
-   Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     Sie können mehrere Konstanten in einer einzelnen Zeile deklariert, obwohl der Code besser lesbar ist, wenn Sie nur einen einzelnen Konstanten pro Zeile deklarieren. Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, sie müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Um mehrere Konstanten in einer einzelnen Zeile deklariert werden.  
  
-   Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Vorgehensweise: Deklarieren einer Konstante](how-to-declare-a-constant.md)
- [Benutzerdefinierte Konstanten](user-defined-constants.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Vorgehensweise: Gruppieren verwandter konstanter Werte](how-to-group-related-constant-values-together.md)
- [Übersicht über Enumerationen](enumerations-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Vorgehensweise: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)

- [Übersicht über Enumerationen](enumerations-overview.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
