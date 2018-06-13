---
title: 'Gewusst wie: Deklarieren einer Konstante (Visual Basic)'
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
ms.openlocfilehash: ce45e4df7f74cd68bde0fb2adba10197a11edb1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649736"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Gewusst wie: Deklarieren einer Konstante (Visual Basic)
Sie verwenden die `Const` -Anweisung zum Deklarieren einer Konstante mit dem Wert. Durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen auf einen Wert an. Sobald eine Konstante deklariert wird, kann nicht geändert oder einen neuer Wert zugewiesen.  
  
 Eine Konstante innerhalb einer Prozedur oder im Deklarationsabschnitt des Moduls, Klasse oder Struktur deklariert werden. Klasse oder Struktur auf Dokumentebene Konstanten sind `Private` standardmäßig jedoch auch als deklariert werden `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene für Code.  
  
 Konstanten müssen einen gültigen symbolischen Namen (die Regeln sind identisch mit denen zum Erstellen von Namen von variabler) und einen numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe) zusammengesetzter Ausdruck.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Um eine Konstante zu deklarieren.  
  
-   Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer hat, enthält die `Const` -Schlüsselwort und in einem Ausdruck, wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, Sie müssen eine Konstante explizit deklarieren, durch Angeben eines Datentyps (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).  
  
     Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Sie Deklarieren einer Konstante, ohne dass einen Datentyp mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Eine Konstante deklariert, die einen explizit angegebenen Datentyp verfügt  
  
-   Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Sie können mehrere Konstanten in einer einzelnen Zeile deklariert, obwohl der Code besser lesbar, wenn Sie nur einen einzelnen Konstanten pro Zeile deklariert ist. Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Um mehrere Konstanten in einer einzelnen Zeile deklariert werden.  
  
-   Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Konstanten und literale Datentypen](constant-and-literal-data-types.md)  
 [Übersicht über Konstanten](constants-overview.md) [wie: Deklarieren einer Konstante](how-to-declare-a-constant.md) [benutzerdefinierte Konstanten](user-defined-constants.md) [Konstanten und Literale Datentypen](constant-and-literal-data-types.md) [Vorgehensweise: Gruppe Verwandter konstanter Werte](how-to-group-related-constant-values-together.md) [Übersicht über Enumerationen](enumerations-overview.md) [wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md) [wie: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md) [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md) [wie: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md) [wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Eine Enumeration verwenden](when-to-use-an-enumeration.md)

 [Übersicht über Enumerationen](enumerations-overview.md)  
 [Übersicht über Konstanten](constants-overview.md)  
 [Vorgehensweise: Deklarieren einer Enumeration](how-to-declare-enumerations.md)  
 [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
