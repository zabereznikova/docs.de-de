---
title: Benutzerdefinierte Konstanten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b1ab1501309823b1565d5198fff25edf2927a2ce
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="606a9-102">Benutzerdefinierte Konstanten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="606a9-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="606a9-103">Eine Konstante ist ein aussagekräftiger Name, der anstelle einer Zahl oder Zeichenfolge, die nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="606a9-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="606a9-104">Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben.</span><span class="sxs-lookup"><span data-stu-id="606a9-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="606a9-105">Konstanten, die definiert werden, durch die Steuerelemente oder Komponenten, mit denen Sie arbeiten können, oder eigene erstellen.</span><span class="sxs-lookup"><span data-stu-id="606a9-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="606a9-106">Konstanten, die Sie selbst erstellen, werden als beschrieben *benutzerdefinierte*.</span><span class="sxs-lookup"><span data-stu-id="606a9-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="606a9-107">Deklarieren von Konstanten mit der `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens.</span><span class="sxs-lookup"><span data-stu-id="606a9-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="606a9-108">Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="606a9-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="606a9-109">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="606a9-109">Const Statement Usage</span></span>  
 <span data-ttu-id="606a9-110">Ein `Const` -Anweisung kann eine mathematische darstellen oder Datum/Uhrzeit Menge:</span><span class="sxs-lookup"><span data-stu-id="606a9-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 <span data-ttu-id="606a9-111">[!code-vb[VbEnumsTask&#10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="606a9-111">[!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span></span>  
  
 <span data-ttu-id="606a9-112">Sie können zudem definieren `String` Konstanten:</span><span class="sxs-lookup"><span data-stu-id="606a9-112">It also can define `String` constants:</span></span>  
  
 <span data-ttu-id="606a9-113">[!code-vb[VbEnumsTask&#13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="606a9-113">[!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span></span>  
  
 <span data-ttu-id="606a9-114">Der Ausdruck auf der rechten Seite des Gleichheitszeichens ( `=` ) ist häufig eine Zahl oder Zeichenfolge, aber auch ein Ausdruck sein, der eine Zahl oder eine Zeichenfolge ergibt (Obwohl dieses Ausdrucks Aufrufe von Funktionen enthalten kann).</span><span class="sxs-lookup"><span data-stu-id="606a9-114">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="606a9-115">Sie können sogar Konstanten basierend auf zuvor definierten Konstanten definieren:</span><span class="sxs-lookup"><span data-stu-id="606a9-115">You can even define constants in terms of previously defined constants:</span></span>  
  
 <span data-ttu-id="606a9-116">[!code-vb[VbEnumsTask&#15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="606a9-116">[!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span></span>  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="606a9-117">Bereich der benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="606a9-117">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="606a9-118">Ein `Const` Scope-Anweisung ist eine Variable, die am gleichen Speicherort identisch.</span><span class="sxs-lookup"><span data-stu-id="606a9-118">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="606a9-119">Sie können den Bereich in einer der folgenden Methoden angeben:</span><span class="sxs-lookup"><span data-stu-id="606a9-119">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="606a9-120">Um eine Konstante zu erstellen, die nur innerhalb einer Prozedur vorhanden ist, deklarieren Sie es in dieser Prozedur.</span><span class="sxs-lookup"><span data-stu-id="606a9-120">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="606a9-121">Um eine Konstante, die für alle Prozeduren in einer Klasse, jedoch nicht für Code außerhalb des Moduls verfügbar zu erstellen, deklarieren Sie ihn in im Deklarationsabschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="606a9-121">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="606a9-122">Um eine Konstante zu erstellen, die für alle Mitglieder einer Assembly, nicht jedoch für Clients außerhalb der Assembly verfügbar ist, deklarieren Sie sie mithilfe der `Friend` -Schlüsselwort in der Sie im Deklarationsabschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="606a9-122">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="606a9-123">Um eine Konstante zur Verfügung, in der gesamten Anwendung zu erstellen, deklarieren Sie sie mithilfe der `Public` -Schlüsselwort in den Deklarationen im Abschnitt der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="606a9-123">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="606a9-124">Weitere Informationen finden Sie unter [Gewusst wie: Deklarieren Sie eine Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="606a9-124">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="606a9-125">Vermeiden von zirkulären Verweisen</span><span class="sxs-lookup"><span data-stu-id="606a9-125">Avoiding Circular References</span></span>  
 <span data-ttu-id="606a9-126">Da Konstanten mithilfe anderer Konstanten definiert werden können, ist es möglich, versehentlich eine *Zyklus*, oder ein Zirkelbezug zwischen zwei oder mehr Konstanten.</span><span class="sxs-lookup"><span data-stu-id="606a9-126">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="606a9-127">Ein Zyklus tritt auf, wenn Sie zwei oder mehr öffentliche Konstanten, die jeweils im Hinblick auf die andere, wie im folgenden Beispiel definiert ist:</span><span class="sxs-lookup"><span data-stu-id="606a9-127">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 <span data-ttu-id="606a9-128">[!code-vb[VbEnumsTask Nr.&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="606a9-128">[!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span></span>  
<span data-ttu-id="606a9-129">[!code-vb[VbEnumsTask&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="606a9-129">[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span></span>  
  
 <span data-ttu-id="606a9-130">Tritt ein Zyklus [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generiert einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="606a9-130">If a cycle occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606a9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="606a9-131">See Also</span></span>  
 <span data-ttu-id="606a9-132">[Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-132">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="606a9-133"> [Konstanten und Literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-133"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="606a9-134"> [Konstanten und Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-134"> [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span></span>  
<span data-ttu-id="606a9-135"> [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-135"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span></span>  
<span data-ttu-id="606a9-136"> [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-136"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="606a9-137"> [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-137"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="606a9-138"> [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-138"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="606a9-139"> [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="606a9-139"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="606a9-140"> [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="606a9-140"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
