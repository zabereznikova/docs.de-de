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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843408"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="fbc03-102">Vorgehensweise: Deklarieren einer Konstante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbc03-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="fbc03-103">Sie verwenden die `Const` Anweisung, um eine Konstante deklariert, und legen Sie dessen Wert.</span><span class="sxs-lookup"><span data-stu-id="fbc03-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="fbc03-104">Durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen auf einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="fbc03-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="fbc03-105">Nachdem eine Konstante deklariert wird, nicht geändert oder einen neuer Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fbc03-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="fbc03-106">Deklarieren von Konstanten in einer Prozedur oder im Deklarationsabschnitt der Module, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="fbc03-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="fbc03-107">Klasse oder Struktur auf Konstanten sind `Private` standardmäßig aber auch als deklariert werden, kann `Public`, `Friend`, `Protected`, oder `Protected Friend` für die entsprechende Zugriffsebene Code.</span><span class="sxs-lookup"><span data-stu-id="fbc03-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="fbc03-108">Die Konstante benötigen einen gültigen symbolischen Namen (die Regeln sind identisch mit denen zum Erstellen von Namen von variabler) und einen Ausdruck aus der numerischen oder Zeichenfolgenausdruck Konstanten und Operatoren (aber keine Funktionsaufrufe).</span><span class="sxs-lookup"><span data-stu-id="fbc03-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="fbc03-109">Um eine Konstante zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fbc03-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="fbc03-110">Schreiben Sie eine Deklaration, Zugriffsspezifizierer hat, enthält, die `Const` -Schlüsselwort und in einem Ausdruck, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="fbc03-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="fbc03-111">Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, Sie müssen eine Konstante explizit deklarieren, indem Sie einen Datentyp angeben (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, oder `String`).</span><span class="sxs-lookup"><span data-stu-id="fbc03-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="fbc03-112">Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Deklarieren einer Konstante können Sie ohne Angabe von einem Datentyp mit einer `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="fbc03-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="fbc03-113">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="fbc03-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="fbc03-114">Weitere Informationen finden Sie unter [Konstanten und Literale Datentypen](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fbc03-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="fbc03-115">Um eine Konstante zu deklarieren, die einen explizit angegebenen Datentyp verfügt</span><span class="sxs-lookup"><span data-stu-id="fbc03-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="fbc03-116">Schreiben Sie eine Deklaration, enthält die `As` -Schlüsselwort und einen expliziten Datentyp eingeben, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="fbc03-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="fbc03-117">Sie können mehrere Konstanten in einer einzelnen Zeile deklariert, obwohl der Code besser lesbar ist, wenn Sie nur einen einzelnen Konstanten pro Zeile deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fbc03-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="fbc03-118">Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, sie müssen alle haben die gleiche Zugriffsebene (`Public`, `Private`, `Friend`, `Protected`, oder `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="fbc03-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="fbc03-119">Um mehrere Konstanten in einer einzelnen Zeile deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fbc03-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="fbc03-120">Trennen Sie die Deklarationen, durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbc03-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fbc03-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbc03-121">See also</span></span>

- [<span data-ttu-id="fbc03-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fbc03-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="fbc03-123">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="fbc03-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fbc03-124">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="fbc03-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fbc03-125">Vorgehensweise: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="fbc03-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="fbc03-126">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="fbc03-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="fbc03-127">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="fbc03-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fbc03-128">Vorgehensweise: Gruppieren verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="fbc03-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="fbc03-129">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fbc03-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="fbc03-130">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fbc03-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="fbc03-131">Vorgehensweise: Finden Sie in einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="fbc03-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="fbc03-132">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="fbc03-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fbc03-133">Vorgehensweise: Durchlaufen einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fbc03-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="fbc03-134">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fbc03-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="fbc03-135">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fbc03-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="fbc03-136">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fbc03-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="fbc03-137">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="fbc03-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fbc03-138">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fbc03-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="fbc03-139">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="fbc03-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fbc03-140">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fbc03-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="fbc03-141">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fbc03-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
