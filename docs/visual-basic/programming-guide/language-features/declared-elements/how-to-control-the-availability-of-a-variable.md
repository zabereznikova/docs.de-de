---
title: 'Vorgehensweise: Steuern der Verfügbarkeit einer Variablen'
ms.date: 07/20/2015
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
ms.openlocfilehash: e6173a0eaa0bf84abb1979711c6df932533c5ce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086113"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="434dc-102">Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="434dc-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>

<span data-ttu-id="434dc-103">Sie steuern die Verfügbarkeit einer Variablen, indem Sie Ihre *Zugriffsebene*angeben.</span><span class="sxs-lookup"><span data-stu-id="434dc-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="434dc-104">Die Zugriffsebene bestimmt, welcher Code über die Berechtigung zum Lesen oder Schreiben der Variablen verfügt.</span><span class="sxs-lookup"><span data-stu-id="434dc-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="434dc-105">Element *Variablen* (auf Modulebene und außerhalb einer Prozedur definiert) werden standardmäßig auf den öffentlichen Zugriff festgelegt. Dies bedeutet, dass jeder Code, den Sie sehen können, darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="434dc-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="434dc-106">Dies kann durch Angabe eines Zugriffsmodifizierers geändert werden.</span><span class="sxs-lookup"><span data-stu-id="434dc-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="434dc-107">*Lokale Variablen* (definiert innerhalb einer Prozedur) weisen nominale öffentliche Zugriffe auf, obwohl nur Code in ihrer Prozedur darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="434dc-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="434dc-108">Sie können die Zugriffsebene einer lokalen Variablen nicht ändern, aber Sie können die Zugriffsebene der Prozedur ändern, in der Sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="434dc-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="434dc-109">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="434dc-109">For more information, see [Access levels in Visual Basic](access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="434dc-110">Privater und öffentlicher Zugriff</span><span class="sxs-lookup"><span data-stu-id="434dc-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="434dc-111">So machen Sie eine Variable nur innerhalb des Moduls, der Klasse oder der Struktur zugänglich</span><span class="sxs-lookup"><span data-stu-id="434dc-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="434dc-112">Platzieren Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="434dc-112">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="434dc-113">Fügen Sie das [private](../../../language-reference/modifiers/private.md) -Schlüsselwort in die `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="434dc-113">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="434dc-114">Sie können die Variable von überall innerhalb des Moduls, der Klasse oder der Struktur lesen oder schreiben, jedoch nicht von außerhalb.</span><span class="sxs-lookup"><span data-stu-id="434dc-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="434dc-115">So machen Sie eine Variable von jedem Code aus zugänglich, der Sie sehen kann</span><span class="sxs-lookup"><span data-stu-id="434dc-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="434dc-116">Platzieren Sie für eine Element Variable die- `Dim` Anweisung für die-Variable in einem Modul, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="434dc-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="434dc-117">Schließt das [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort in die- `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="434dc-117">Include the [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="434dc-118">Sie können in jedem Code, der mit der Assembly interagiert, Lese-oder Schreibzugriff auf die Variable erhalten.</span><span class="sxs-lookup"><span data-stu-id="434dc-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="434dc-119">- oder -</span><span class="sxs-lookup"><span data-stu-id="434dc-119">-or-</span></span>  
  
1. <span data-ttu-id="434dc-120">Platzieren Sie für eine lokale Variable die- `Dim` Anweisung für die Variable in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="434dc-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="434dc-121">Fügen Sie das- `Public` Schlüsselwort nicht in die- `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="434dc-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="434dc-122">Sie können die Variable von jedem beliebigen Ort innerhalb des Verfahrens aus lesen oder schreiben, jedoch nicht von außerhalb.</span><span class="sxs-lookup"><span data-stu-id="434dc-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="434dc-123">Geschützter Zugriff und Friend-Zugriff</span><span class="sxs-lookup"><span data-stu-id="434dc-123">Protected and Friend Access</span></span>  

 <span data-ttu-id="434dc-124">Sie können die Zugriffsebene einer Variablen auf Ihre Klasse und alle abgeleiteten Klassen oder auf Ihre Assembly beschränken.</span><span class="sxs-lookup"><span data-stu-id="434dc-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="434dc-125">Sie können auch die Union dieser Einschränkungen angeben, die den Zugriff aus Code in einer beliebigen abgeleiteten Klasse oder an einer beliebigen anderen Stelle in derselben Assembly zulässt.</span><span class="sxs-lookup"><span data-stu-id="434dc-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="434dc-126">Sie geben diese Union an, indem Sie die `Protected` `Friend` Schlüsselwörter und in der gleichen Deklaration kombinieren.</span><span class="sxs-lookup"><span data-stu-id="434dc-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="434dc-127">So machen Sie eine Variable nur innerhalb ihrer Klasse und abgeleiteter Klassen zugänglich</span><span class="sxs-lookup"><span data-stu-id="434dc-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="434dc-128">Platzieren Sie die- `Dim` Anweisung für die Variable in einer Klasse, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="434dc-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="434dc-129">Schließen Sie das [geschützte](../../../language-reference/modifiers/protected.md) Schlüsselwort in die- `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="434dc-129">Include the [Protected](../../../language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="434dc-130">Sie können die Variable von jedem beliebigen Ort innerhalb der Klasse aus lesen oder in eine beliebige Klasse schreiben, die davon abgeleitet ist, aber nicht von außerhalb einer Klasse in der Ableitung-Kette.</span><span class="sxs-lookup"><span data-stu-id="434dc-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="434dc-131">So machen Sie eine Variable nur innerhalb derselben Assembly zugänglich</span><span class="sxs-lookup"><span data-stu-id="434dc-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="434dc-132">Platzieren Sie die- `Dim` Anweisung für die-Variable in einem Modul, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="434dc-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="434dc-133">Fügen Sie das [Friend](../../../language-reference/modifiers/friend.md) -Schlüsselwort in die `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="434dc-133">Include the [Friend](../../../language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="434dc-134">Sie können die Variable von einem beliebigen Speicherort innerhalb des Moduls, der Klasse oder Struktur sowie von einem beliebigen Code in derselben Assembly, aber nicht von außerhalb der Assembly lesen oder schreiben.</span><span class="sxs-lookup"><span data-stu-id="434dc-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="434dc-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="434dc-135">Example</span></span>  

 <span data-ttu-id="434dc-136">Das folgende Beispiel zeigt Deklarationen von Variablen mit den `Public` `Protected` `Friend` Zugriffsebenen,,, `Protected Friend` und `Private` .</span><span class="sxs-lookup"><span data-stu-id="434dc-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="434dc-137">Beachten Sie, dass `Dim` Sie das-Schlüsselwort nicht einschließen müssen, wenn die-Anweisung eine Zugriffsebene angibt `Dim` .</span><span class="sxs-lookup"><span data-stu-id="434dc-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="434dc-138">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="434dc-138">.NET Framework Security</span></span>  

 <span data-ttu-id="434dc-139">Wenn die Zugriffsebene einer Variablen restriktiver ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="434dc-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434dc-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="434dc-140">See also</span></span>

- [<span data-ttu-id="434dc-141">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="434dc-141">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="434dc-142">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="434dc-142">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="434dc-143">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="434dc-143">Public</span></span>](../../../language-reference/modifiers/public.md)
- [<span data-ttu-id="434dc-144">Gebieten</span><span class="sxs-lookup"><span data-stu-id="434dc-144">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="434dc-145">Friend</span><span class="sxs-lookup"><span data-stu-id="434dc-145">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="434dc-146">Privat</span><span class="sxs-lookup"><span data-stu-id="434dc-146">Private</span></span>](../../../language-reference/modifiers/private.md)
