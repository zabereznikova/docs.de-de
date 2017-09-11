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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b7fc499336c2b5db3b4d2fe9c0cd11799ea0ad77
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="53058-102">Gewusst wie: Deklarieren einer Konstante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53058-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="53058-103">Sie verwenden die `Const` -Anweisung zum Deklarieren einer Konstante und legen Sie seinen Wert.</span><span class="sxs-lookup"><span data-stu-id="53058-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="53058-104">Durch Deklarieren einer Konstante weisen Sie einen aussagekräftigen Namen, einen Wert.</span><span class="sxs-lookup"><span data-stu-id="53058-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="53058-105">Nachdem eine Konstante deklariert wird, nicht geändert oder einen neuer Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="53058-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="53058-106">Deklarieren von Konstanten in einer Prozedur oder im Deklarationsabschnitt des Moduls, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="53058-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="53058-107">Klasse oder Struktur auf Konstanten sind `Private` standardmäßig jedoch auch als deklariert werden `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene für Code.</span><span class="sxs-lookup"><span data-stu-id="53058-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="53058-108">Die Konstante muss einen gültigen symbolischen Namen (die Regeln sind identisch mit denen für das Erstellen von Variablennamen) und einen Ausdruck aus der numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe) enthalten.</span><span class="sxs-lookup"><span data-stu-id="53058-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="53058-109">So deklarieren Sie eine Konstante</span><span class="sxs-lookup"><span data-stu-id="53058-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="53058-110">Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer, enthält die `Const` -Schlüsselwort und einen Ausdruck wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="53058-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     <span data-ttu-id="53058-111">[!code-vb[VbEnumsTask&#8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="53058-111">[!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span></span>  
  
     <span data-ttu-id="53058-112">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie eine Konstante explizit durch Angabe eines Datentyps deklarieren (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).</span><span class="sxs-lookup"><span data-stu-id="53058-112">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="53058-113">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, kann zum Deklarieren von Konstanten ohne Angabe eines Datentyps mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="53058-113">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="53058-114">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="53058-114">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="53058-115">Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="53058-115">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="53058-116">Eine Konstante deklarieren, die einen explizit angegebenen Datentyp verfügt</span><span class="sxs-lookup"><span data-stu-id="53058-116">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="53058-117">Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="53058-117">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     <span data-ttu-id="53058-118">[!code-vb[VbEnumsTask&#9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="53058-118">[!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span></span>  
  
     <span data-ttu-id="53058-119">In einer einzelnen Zeile können mehrere Konstanten deklariert werden, obwohl der Code leichter lesbar ist, wenn Sie nur eine einzelne Konstante pro Zeile deklarieren.</span><span class="sxs-lookup"><span data-stu-id="53058-119">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="53058-120">Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="53058-120">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="53058-121">Deklarieren Sie mehrere Konstanten in einer einzelnen Zeile</span><span class="sxs-lookup"><span data-stu-id="53058-121">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="53058-122">Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53058-122">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="53058-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53058-123">See Also</span></span>  
 <span data-ttu-id="53058-124">[Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53058-124">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="53058-125"> [Konstanten und Literale Datentypen](constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="53058-125"> [Constant and Literal Data Types](constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="53058-126"> [Übersicht über Konstanten](constants-overview.md)
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
 [bei einer Enumeration](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="53058-126"> [Constants Overview](constants-overview.md)
 [How to: Declare A Constant](how-to-declare-a-constant.md)
 [User-Defined Constants](user-defined-constants.md)
 [Constant and Literal Data Types](constant-and-literal-data-types.md)
 [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md)
 [Enumerations Overview](enumerations-overview.md)
 [How to: Declare Enumerations](how-to-declare-enumerations.md)
 [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md)
 [Enumerations and Name Qualification](enumerations-and-name-qualification.md)
 [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md)
 [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 <span data-ttu-id="53058-127">[Übersicht über Enumerationen](enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="53058-127">[Enumerations Overview](enumerations-overview.md) </span></span>  
<span data-ttu-id="53058-128"> [Übersicht über Konstanten](constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="53058-128"> [Constants Overview](constants-overview.md) </span></span>  
<span data-ttu-id="53058-129"> [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="53058-129"> [How to: Declare an Enumeration](how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="53058-130"> [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="53058-130"> [Enumerations and Name Qualification](enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="53058-131"> [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53058-131"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="53058-132"> [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="53058-132"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

