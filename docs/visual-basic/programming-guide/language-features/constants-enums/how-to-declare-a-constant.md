---
title: 'Gewusst wie: Deklarieren einer Konstante (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
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
ms.openlocfilehash: 401d0feb85fccf94a25308d38c3c75198ef9294c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a>Gewusst wie: Deklarieren einer Konstante (Visual Basic)
Sie verwenden die `Const` -Anweisung zum Deklarieren einer Konstante und legen Sie seinen Wert. Durch Deklarieren einer Konstante weisen Sie einen aussagekräftigen Namen, einen Wert. Nachdem eine Konstante deklariert wird, nicht geändert oder einen neuer Wert zugewiesen.  
  
 Deklarieren von Konstanten in einer Prozedur oder im Deklarationsabschnitt des Moduls, Klasse oder Struktur. Klasse oder Struktur auf Konstanten sind `Private` standardmäßig jedoch auch als deklariert werden `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene für Code.  
  
 Die Konstante muss einen gültigen symbolischen Namen (die Regeln sind identisch mit denen für das Erstellen von Variablennamen) und einen Ausdruck aus der numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe) enthalten.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-declare-a-constant"></a>So deklarieren Sie eine Konstante  
  
-   Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer, enthält die `Const` -Schlüsselwort und einen Ausdruck wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask&#8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie eine Konstante explizit durch Angabe eines Datentyps deklarieren (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).  
  
     Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, kann zum Deklarieren von Konstanten ohne Angabe eines Datentyps mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Eine Konstante deklarieren, die einen explizit angegebenen Datentyp verfügt  
  
-   Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:  
  
     [!code-vb[VbEnumsTask&#9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     In einer einzelnen Zeile können mehrere Konstanten deklariert werden, obwohl der Code leichter lesbar ist, wenn Sie nur eine einzelne Konstante pro Zeile deklarieren. Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Deklarieren Sie mehrere Konstanten in einer einzelnen Zeile  
  
-   Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Konstanten und Literale Datentypen](constant-and-literal-data-types.md)   
 [Übersicht über Konstanten](constants-overview.md)
 [Gewusst wie: Deklarieren einer Konstante](how-to-declare-a-constant.md)
 [benutzerdefinierte Konstanten](user-defined-constants.md)
 [Konstanten und Literale Datentypen](constant-and-literal-data-types.md)
 [wie: Gruppieren verwandter konstanter Werte](how-to-group-related-constant-values-together.md)
 [Übersicht über Enumerationen](enumerations-overview.md)
 [wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
 [wie: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
 [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
 [wie: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md)
 [Gewusst wie: Bestimmen der Zeichenfolge Ein Enumerationswert zugeordneten](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [bei einer Enumeration](when-to-use-an-enumeration.md)

 [Übersicht über Enumerationen](enumerations-overview.md)   
 [Übersicht über Konstanten](constants-overview.md)   
 [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)   
 [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

