---
title: Benutzerdefinierte Konstanten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: b4a7e2b63b930b98ee082c0104c24f6857b5b35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648774"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="3fd48-102">Benutzerdefinierte Konstanten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fd48-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="3fd48-103">Eine Konstante ist, einen aussagekräftigen Namen, der anstelle einer Zahl oder eine Zeichenfolge, die nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="3fd48-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="3fd48-104">Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben.</span><span class="sxs-lookup"><span data-stu-id="3fd48-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="3fd48-105">Konstanten, die durch die Steuerelemente für die Arbeit mit Komponenten definiert werden können, oder eigene erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fd48-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="3fd48-106">Konstanten, die Sie selbst erstellen, werden als beschrieben *benutzerdefinierte*.</span><span class="sxs-lookup"><span data-stu-id="3fd48-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="3fd48-107">Deklarieren von Konstanten mit der `Const` verwenden Sie dieselben Richtlinien zum Erstellen eines Variablennamens-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3fd48-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="3fd48-108">Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3fd48-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="3fd48-109">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3fd48-109">Const Statement Usage</span></span>  
 <span data-ttu-id="3fd48-110">Ein `Const` -Anweisung kann eine mathematische Darstellung oder Datum/Uhrzeit Menge:</span><span class="sxs-lookup"><span data-stu-id="3fd48-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 <span data-ttu-id="3fd48-111">Sie können zudem definieren `String` Konstanten:</span><span class="sxs-lookup"><span data-stu-id="3fd48-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 <span data-ttu-id="3fd48-112">Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) häufig eine Zahl oder Zeichenfolgenliteral, sondern kann auch ein Ausdruck, der eine Zahl oder eine Zeichenfolge ausgibt (Obwohl dieses Ausdrucks Aufrufen von Funktionen enthalten kann) sein.</span><span class="sxs-lookup"><span data-stu-id="3fd48-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="3fd48-113">Sie können auch Konstanten in Bezug auf die zuvor definierten Konstanten definieren:</span><span class="sxs-lookup"><span data-stu-id="3fd48-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="3fd48-114">Umfang der benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="3fd48-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="3fd48-115">Ein `Const` Scope-Anweisung ist identisch mit der eine Variable deklariert, die am gleichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="3fd48-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="3fd48-116">Sie können den Bereich in einem der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="3fd48-116">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="3fd48-117">Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie es während dieser Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="3fd48-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="3fd48-118">Um eine Konstante, die für alle Prozeduren innerhalb einer Klasse, jedoch nicht für Code außerhalb des Moduls verfügbar zu erstellen, deklarieren sie im Deklarationsabschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fd48-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="3fd48-119">Um eine Konstante zu erstellen, die auf alle Elemente einer Assembly, nicht jedoch für Clients außerhalb der Assembly verfügbar ist, deklarieren Sie sie mithilfe der `Friend` Schlüsselwort im Deklarationsabschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fd48-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="3fd48-120">Um eine Konstante zur Verfügung, in der gesamten Anwendung zu erstellen, deklarieren Sie sie mithilfe der `Public` Schlüsselwort in den Deklarationen im Abschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fd48-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="3fd48-121">Weitere Informationen finden Sie unter [wie: Deklarieren Sie eine Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="3fd48-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="3fd48-122">Zirkelverweise zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="3fd48-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="3fd48-123">Da Konstanten im Hinblick auf andere Konstanten definiert werden können, ist es möglich, versehentlich erstellen eine *der Reihe nach*, oder ein Zirkelbezug zwischen zwei oder mehr Konstanten.</span><span class="sxs-lookup"><span data-stu-id="3fd48-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="3fd48-124">Ein Zyklus tritt auf, wenn Sie mindestens zwei öffentliche Konstanten, von die jede im Hinblick auf andere, wie im folgenden Beispiel definiert ist:</span><span class="sxs-lookup"><span data-stu-id="3fd48-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 <span data-ttu-id="3fd48-125">Wenn eine Schleife auftritt, generiert Visual Basic einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="3fd48-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd48-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fd48-126">See Also</span></span>  
 [<span data-ttu-id="3fd48-127">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3fd48-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="3fd48-128">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="3fd48-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="3fd48-129">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3fd48-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [<span data-ttu-id="3fd48-130">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3fd48-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="3fd48-131">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3fd48-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="3fd48-132">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="3fd48-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="3fd48-133">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="3fd48-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="3fd48-134">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="3fd48-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="3fd48-135">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3fd48-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
