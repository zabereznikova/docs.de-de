---
title: Benutzerdefinierte Konstanten
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 14f3de39eb8d8e6820e2b40792a8e8e57217e410
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414375"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="c8786-102">Benutzerdefinierte Konstanten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8786-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="c8786-103">Eine Konstante ist ein sinnvoller Name, der den Speicherort einer Zahl oder Zeichenfolge annimmt, der sich nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="c8786-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="c8786-104">Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben.</span><span class="sxs-lookup"><span data-stu-id="c8786-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="c8786-105">Sie können Konstanten verwenden, die von den Steuerelementen oder Komponenten definiert werden, mit denen Sie arbeiten, oder Sie können eine eigene erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8786-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="c8786-106">Die von Ihnen selbst erstellten Konstanten werden als *Benutzer definiert*beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8786-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="c8786-107">Sie deklarieren eine Konstante mit der- `Const` Anweisung, wobei Sie die gleichen Richtlinien verwenden, die Sie zum Erstellen eines Variablen namens verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="c8786-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="c8786-108">Wenn `Option Strict` ist `On` , müssen Sie den Konstantentyp explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8786-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="c8786-109">Verwendung der Konstanten Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8786-109">Const Statement Usage</span></span>  
 <span data-ttu-id="c8786-110">Eine- `Const` Anweisung kann eine mathematische oder Datums-/Uhrzeitmenge darstellen:</span><span class="sxs-lookup"><span data-stu-id="c8786-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="c8786-111">Außerdem können Konstanten definiert werden `String` :</span><span class="sxs-lookup"><span data-stu-id="c8786-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="c8786-112">Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) ist oft eine Zahl oder eine Literalzeichenfolge, es kann sich jedoch auch um einen Ausdruck handeln, der zu einer Zahl oder Zeichenfolge führt (obwohl dieser Ausdruck keine Aufrufe von Funktionen enthalten kann).</span><span class="sxs-lookup"><span data-stu-id="c8786-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="c8786-113">Sie können auch Konstanten in Bezug auf zuvor definierte Konstanten definieren:</span><span class="sxs-lookup"><span data-stu-id="c8786-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="c8786-114">Bereich von benutzerdefinierten Konstanten</span><span class="sxs-lookup"><span data-stu-id="c8786-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="c8786-115">Der Gültigkeits `Const` Bereich einer Anweisung ist identisch mit der einer Variablen, die am gleichen Speicherort deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8786-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="c8786-116">Der Bereich kann auf eine der folgenden Arten angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="c8786-116">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="c8786-117">Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie Sie in dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="c8786-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="c8786-118">Um eine Konstante zu erstellen, die für alle Prozeduren in einer Klasse, aber nicht für Code außerhalb dieses Moduls verfügbar ist, deklarieren Sie Sie im Deklarations Abschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="c8786-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="c8786-119">Um eine Konstante zu erstellen, die für alle Member einer Assembly, jedoch nicht für externe Clients der Assembly verfügbar ist, deklarieren Sie Sie mithilfe des- `Friend` Schlüssel Worts im Deklarations Abschnitt der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c8786-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="c8786-120">Um eine in der gesamten Anwendung verfügbare Konstante zu erstellen, deklarieren Sie Sie mithilfe des- `Public` Schlüssel Worts im Deklarations Abschnitt der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c8786-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="c8786-121">Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Konstanten](how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="c8786-121">For more information, see [How to: Declare A Constant](how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="c8786-122">Vermeiden von Zirkel verweisen</span><span class="sxs-lookup"><span data-stu-id="c8786-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="c8786-123">Da Konstanten in Bezug auf andere Konstanten definiert werden können, ist es möglich, versehentlich einen *Cycle*oder Zirkel Verweis zwischen mindestens zwei Konstanten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8786-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="c8786-124">Ein Durchlauf tritt auf, wenn Sie über zwei oder mehr öffentliche Konstanten verfügen, von denen jede in Bezug auf die andere definiert ist, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c8786-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="c8786-125">Wenn eine Zyklen auftritt, generiert Visual Basic einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="c8786-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8786-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8786-126">See also</span></span>

- [<span data-ttu-id="c8786-127">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8786-127">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
- [<span data-ttu-id="c8786-128">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="c8786-128">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="c8786-129">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c8786-129">Constants and Enumerations</span></span>](index.md)
- [<span data-ttu-id="c8786-130">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c8786-130">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="c8786-131">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c8786-131">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="c8786-132">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="c8786-132">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="c8786-133">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="c8786-133">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="c8786-134">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="c8786-134">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="c8786-135">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c8786-135">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
