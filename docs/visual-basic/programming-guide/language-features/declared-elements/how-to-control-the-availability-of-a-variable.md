---
title: "Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 004fb101661fadeaee084e1f9374ca8332ac7234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="0c90e-102">Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c90e-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="0c90e-103">Sie steuern die Verfügbarkeit einer Variablen durch Angabe seiner *Zugriffsebene*.</span><span class="sxs-lookup"><span data-stu-id="0c90e-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="0c90e-104">Die Zugriffsebene bestimmt, welcher Code verfügt über die Berechtigung zum Lesen oder Schreiben auf die Variable.</span><span class="sxs-lookup"><span data-stu-id="0c90e-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="0c90e-105">*Membervariablen* (auf Modulebene und außerhalb einer Prozedur definiert) standardmäßig öffentlichen Zugriff auf, d. h. jeglicher Code, der sie angezeigt werden kann darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0c90e-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="0c90e-106">Sie können dies ändern, indem Sie einen Zugriffsmodifizierer angeben.</span><span class="sxs-lookup"><span data-stu-id="0c90e-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="0c90e-107">*Lokale Variablen* (innerhalb einer Prozedur definiert) nominell öffentlichen Zugriff haben, obwohl nur Code innerhalb ihrer Prozedur darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0c90e-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="0c90e-108">Die Zugriffsebene einer lokalen Variablen kann nicht geändert werden, aber Sie können die Zugriffsebene der Prozedur, die es enthält ändern.</span><span class="sxs-lookup"><span data-stu-id="0c90e-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="0c90e-109">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0c90e-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="0c90e-110">Privater und öffentlicher Zugriff</span><span class="sxs-lookup"><span data-stu-id="0c90e-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="0c90e-111">Eine Variable nur innerhalb seiner-Modul, Klasse oder Struktur zugänglich gemacht</span><span class="sxs-lookup"><span data-stu-id="0c90e-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="0c90e-112">Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0c90e-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="0c90e-113">Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0c90e-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="0c90e-114">Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb das Modul, Klasse oder Struktur, jedoch nicht von außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="0c90e-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="0c90e-115">Um eine Variable von einem beliebigen Code verfügbar, die sie anzeigen können</span><span class="sxs-lookup"><span data-stu-id="0c90e-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="0c90e-116">Platzieren Sie nach einer Membervariable der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0c90e-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="0c90e-117">Enthalten die [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0c90e-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="0c90e-118">Sie können lesen oder Schreiben auf die Variable von einem beliebigen Code, die Interoperabilität mit der Assembly.</span><span class="sxs-lookup"><span data-stu-id="0c90e-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="0c90e-119">- oder - </span><span class="sxs-lookup"><span data-stu-id="0c90e-119">-or-</span></span>  
  
1.  <span data-ttu-id="0c90e-120">Platzieren Sie für eine lokale Variable, die `Dim` -Anweisung für die Variable innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0c90e-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="0c90e-121">Schließen Sie nicht die `Public` -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0c90e-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="0c90e-122">Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Prozedur, jedoch nicht von außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="0c90e-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="0c90e-123">Geschützte und Friend-Zugriff</span><span class="sxs-lookup"><span data-stu-id="0c90e-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="0c90e-124">Sie können die Zugriffsebene einer Variablen auf ihre Klasse und keine abgeleiteten Klassen oder in einer Assembly einschränken.</span><span class="sxs-lookup"><span data-stu-id="0c90e-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="0c90e-125">Sie können auch die Kombination dieser Einschränkungen angeben, die Zugriff von Code in einer abgeleiteten Klasse oder in eine beliebige andere Stelle in der gleichen Assembly erlaubt.</span><span class="sxs-lookup"><span data-stu-id="0c90e-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="0c90e-126">Sie geben diese Union kombinierten der `Protected` und `Friend` Schlüsselwörter in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="0c90e-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="0c90e-127">Um eine Variable nur innerhalb der Klasse und alle abgeleiteten Klassen zugänglich zu machen</span><span class="sxs-lookup"><span data-stu-id="0c90e-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="0c90e-128">Ort der `Dim` -Anweisung für die Variable innerhalb einer Klasse, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0c90e-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="0c90e-129">Enthalten die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0c90e-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="0c90e-130">Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Klasse sowie innerhalb eine Klasse abgeleitet, jedoch nicht von außerhalb einer Klasse in der Ableitungskette.</span><span class="sxs-lookup"><span data-stu-id="0c90e-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="0c90e-131">Eine Variable kann nur zugegriffen werden innerhalb der gleichen Assembly vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0c90e-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="0c90e-132">Ort der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0c90e-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="0c90e-133">Enthalten die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0c90e-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="0c90e-134">Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle in das Modul, Klasse oder Struktur, sowie von einem beliebigen Code in derselben Assembly, jedoch nicht von außerhalb der Assembly.</span><span class="sxs-lookup"><span data-stu-id="0c90e-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c90e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c90e-135">Example</span></span>  
 <span data-ttu-id="0c90e-136">Das folgende Beispiel zeigt die Deklarationen von Variablen mit `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private` Zugriffsebenen.</span><span class="sxs-lookup"><span data-stu-id="0c90e-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="0c90e-137">Beachten Sie, dass bei der `Dim` -Anweisung gibt eine Zugriffsebene, müssen Sie nicht einschließen der `Dim` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="0c90e-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="0c90e-138">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0c90e-138">.NET Framework Security</span></span>  
 <span data-ttu-id="0c90e-139">Die restriktivere Zugriffsebene einer Variablen, desto geringer ist die Wahrscheinlichkeit, die bösartiger Code falsche vornehmen können verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c90e-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c90e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c90e-140">See Also</span></span>  
 [<span data-ttu-id="0c90e-141">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c90e-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="0c90e-142">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c90e-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="0c90e-143">Public</span><span class="sxs-lookup"><span data-stu-id="0c90e-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="0c90e-144">Protected</span><span class="sxs-lookup"><span data-stu-id="0c90e-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="0c90e-145">Friend</span><span class="sxs-lookup"><span data-stu-id="0c90e-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="0c90e-146">Private</span><span class="sxs-lookup"><span data-stu-id="0c90e-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
