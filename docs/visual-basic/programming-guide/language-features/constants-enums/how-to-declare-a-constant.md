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
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="fc8e8-102">Gewusst wie: Deklarieren einer Konstante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc8e8-102">How to: Declare A Constant (Visual Basic)</span></span>

<span data-ttu-id="fc8e8-103">Verwenden Sie die `Const` -Anweisung, um eine Konstante zu deklarieren und ihren Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="fc8e8-104">Durch das Deklarieren einer Konstanten weisen Sie einem Wert einen aussagekräftigen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="fc8e8-105">Nachdem eine Konstante deklariert wurde, kann Sie nicht geändert werden, oder es kann kein neuer Wert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="fc8e8-106">Sie deklarieren eine Konstante innerhalb einer Prozedur oder im Deklarations Abschnitt eines Moduls, einer Klasse oder einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="fc8e8-107">Konstanten auf Klassen-oder Struktur Ebene sind `Private` standardmäßig, können aber auch als `Public` , `Friend` , `Protected` oder `Protected Friend` für die entsprechende Ebene des Code Zugriffs deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="fc8e8-108">Die Konstante muss einen gültigen symbolischen Namen aufweisen (die Regeln sind identisch mit denen für das Erstellen von Variablennamen), und ein Ausdruck, der aus numerischen oder Zeichen folgen Konstanten und Operatoren besteht (aber keine Funktionsaufrufe).</span><span class="sxs-lookup"><span data-stu-id="fc8e8-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="fc8e8-109">So deklarieren Sie eine Konstante</span><span class="sxs-lookup"><span data-stu-id="fc8e8-109">To declare a constant</span></span>  
  
- <span data-ttu-id="fc8e8-110">Schreiben Sie eine Deklaration, die einen Zugriffsspezifizierer, das `Const` Schlüsselwort und einen Ausdruck enthält, wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc8e8-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="fc8e8-111">Wenn die [Option Infer](../../../language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../language-reference/statements/option-strict-statement.md) ist `On` , müssen Sie eine Konstante explizit deklarieren, indem Sie einen-Datentyp angeben ( `Boolean` , `Byte` , `Char` , `DateTime` , `Decimal` , `Double` , `Integer` , `Long` , `Short` , `Single` oder `String` ).</span><span class="sxs-lookup"><span data-stu-id="fc8e8-111">When [Option Infer](../../../language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="fc8e8-112">Wenn auf oder festgelegt ist `Option Infer` `On` `Option Strict` `Off` , können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer- `As` Klausel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="fc8e8-113">Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="fc8e8-114">Weitere Informationen finden Sie unter [Constant-und literaldatentypen](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc8e8-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="fc8e8-115">So deklarieren Sie eine Konstante, die über einen explizit angegebenen Datentyp verfügt</span><span class="sxs-lookup"><span data-stu-id="fc8e8-115">To declare a constant that has an explicitly stated data type</span></span>  
  
- <span data-ttu-id="fc8e8-116">Schreiben Sie eine Deklaration, die das `As` -Schlüsselwort und einen expliziten-Datentyp enthält, wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc8e8-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="fc8e8-117">Sie können mehrere Konstanten in einer einzelnen Zeile deklarieren, obwohl der Code besser lesbar ist, wenn Sie nur eine einzelne Konstante pro Zeile deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fc8e8-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="fc8e8-118">Wenn Sie mehrere Konstanten in einer einzelnen Zeile deklarieren, müssen diese alle die gleiche Zugriffsebene aufweisen ( `Public` ,, `Private` `Friend` , `Protected` oder `Protected Friend` ).</span><span class="sxs-lookup"><span data-stu-id="fc8e8-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="fc8e8-119">So deklarieren Sie mehrere Konstanten in einer einzelnen Zeile</span><span class="sxs-lookup"><span data-stu-id="fc8e8-119">To declare multiple constants on a single line</span></span>  
  
- <span data-ttu-id="fc8e8-120">Trennen Sie die Deklarationen durch ein Komma und ein Leerzeichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc8e8-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fc8e8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc8e8-121">See also</span></span>

- [<span data-ttu-id="fc8e8-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc8e8-122">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
- [<span data-ttu-id="fc8e8-123">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fc8e8-124">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="fc8e8-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fc8e8-125">Vorgehensweise: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="fc8e8-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="fc8e8-126">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="fc8e8-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="fc8e8-127">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fc8e8-128">Vorgehensweise: Gruppieren verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="fc8e8-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="fc8e8-129">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="fc8e8-130">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fc8e8-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="fc8e8-131">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="fc8e8-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="fc8e8-132">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="fc8e8-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fc8e8-133">Vorgehensweise: Durchlaufen einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fc8e8-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="fc8e8-134">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc8e8-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="fc8e8-135">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="fc8e8-136">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="fc8e8-137">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="fc8e8-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fc8e8-138">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="fc8e8-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="fc8e8-139">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="fc8e8-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fc8e8-140">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc8e8-140">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="fc8e8-141">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fc8e8-141">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
