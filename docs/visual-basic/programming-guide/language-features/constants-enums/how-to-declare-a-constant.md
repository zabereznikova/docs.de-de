---
title: 'Gewusst wie: Deklarieren einer Konstante (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.constant
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554f659e060087228fb43efd8b9d06103e21e980
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="89d8d-102">Gewusst wie: Deklarieren einer Konstante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89d8d-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="89d8d-103">Sie verwenden die `Const` -Anweisung zum Deklarieren einer Konstante mit dem Wert.</span><span class="sxs-lookup"><span data-stu-id="89d8d-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="89d8d-104">Durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen auf einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="89d8d-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="89d8d-105">Sobald eine Konstante deklariert wird, kann nicht geändert oder einen neuer Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="89d8d-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="89d8d-106">Eine Konstante innerhalb einer Prozedur oder im Deklarationsabschnitt des Moduls, Klasse oder Struktur deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="89d8d-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="89d8d-107">Klasse oder Struktur auf Dokumentebene Konstanten sind `Private` standardmäßig jedoch auch als deklariert werden `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene für Code.</span><span class="sxs-lookup"><span data-stu-id="89d8d-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="89d8d-108">Konstanten müssen einen gültigen symbolischen Namen (die Regeln sind identisch mit denen zum Erstellen von Namen von variabler) und einen numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe) zusammengesetzter Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="89d8d-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="89d8d-109">Um eine Konstante zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="89d8d-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="89d8d-110">Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer hat, enthält die `Const` -Schlüsselwort und in einem Ausdruck, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="89d8d-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     <span data-ttu-id="89d8d-111">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, Sie müssen eine Konstante explizit deklarieren, durch Angeben eines Datentyps (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).</span><span class="sxs-lookup"><span data-stu-id="89d8d-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="89d8d-112">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Sie Deklarieren einer Konstante, ohne dass einen Datentyp mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="89d8d-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="89d8d-113">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="89d8d-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="89d8d-114">Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="89d8d-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="89d8d-115">Eine Konstante deklariert, die einen explizit angegebenen Datentyp verfügt</span><span class="sxs-lookup"><span data-stu-id="89d8d-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="89d8d-116">Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="89d8d-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     <span data-ttu-id="89d8d-117">Sie können mehrere Konstanten in einer einzelnen Zeile deklariert, obwohl der Code besser lesbar, wenn Sie nur einen einzelnen Konstanten pro Zeile deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="89d8d-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="89d8d-118">Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="89d8d-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="89d8d-119">Um mehrere Konstanten in einer einzelnen Zeile deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="89d8d-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="89d8d-120">Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="89d8d-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="89d8d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89d8d-121">See Also</span></span>  
 [<span data-ttu-id="89d8d-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89d8d-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="89d8d-123">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="89d8d-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)  
 <span data-ttu-id="89d8d-124">[Übersicht über Konstanten](constants-overview.md) [wie: Deklarieren einer Konstante](how-to-declare-a-constant.md) [benutzerdefinierte Konstanten](user-defined-constants.md) [Konstanten und Literale Datentypen](constant-and-literal-data-types.md) [Vorgehensweise: Gruppe Verwandter konstanter Werte](how-to-group-related-constant-values-together.md) [Übersicht über Enumerationen](enumerations-overview.md) [wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md) [wie: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md) [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md) [wie: Durchlaufen einer Enumeration](how-to-iterate-through-an-enumeration.md) [wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Eine Enumeration verwenden](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="89d8d-124">[Constants Overview](constants-overview.md) [How to: Declare A Constant](how-to-declare-a-constant.md) [User-Defined Constants](user-defined-constants.md) [Constant and Literal Data Types](constant-and-literal-data-types.md) [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md) [Enumerations Overview](enumerations-overview.md) [How to: Declare Enumerations](how-to-declare-enumerations.md) [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md) [Enumerations and Name Qualification](enumerations-and-name-qualification.md) [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md) [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md) [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 [<span data-ttu-id="89d8d-125">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="89d8d-125">Enumerations Overview</span></span>](enumerations-overview.md)  
 [<span data-ttu-id="89d8d-126">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="89d8d-126">Constants Overview</span></span>](constants-overview.md)  
 [<span data-ttu-id="89d8d-127">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="89d8d-127">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)  
 [<span data-ttu-id="89d8d-128">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="89d8d-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)  
 [<span data-ttu-id="89d8d-129">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89d8d-129">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="89d8d-130">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="89d8d-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
