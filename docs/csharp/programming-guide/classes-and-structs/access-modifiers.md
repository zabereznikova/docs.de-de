---
title: Zugriffsmodifizierer (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="743c0-102">Zugriffsmodifizierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="743c0-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="743c0-103">Alle Typen und Typmember haben eine Zugriffsebene, die steuert, ob sie von anderem Code in Ihrer Assembly oder anderen Assemblys verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="743c0-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="743c0-104">Sie können die folgenden Zugriffsmodifizierer verwenden, um den Zugriff auf einen Typ oder Member anzugeben, wenn Sie sie deklarieren:</span><span class="sxs-lookup"><span data-stu-id="743c0-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="743c0-105">public</span><span class="sxs-lookup"><span data-stu-id="743c0-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="743c0-106">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="743c0-107">private</span><span class="sxs-lookup"><span data-stu-id="743c0-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="743c0-108">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder Struktur zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="743c0-109">protected</span><span class="sxs-lookup"><span data-stu-id="743c0-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="743c0-110">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder Struktur oder in einer Klasse, die von dieser Klasse abgeleitet ist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="743c0-111">internal</span><span class="sxs-lookup"><span data-stu-id="743c0-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="743c0-112">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="743c0-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="743c0-113">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly, in der er deklariert ist, oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="743c0-114">Zugriff von einer anderen Assembly muss innerhalb einer Klassendeklaration erfolgen, die von der Klasse abgeleitet ist, in der das geschützte interne Element deklariert wird, und dies muss über eine Instanz des Typs der abgeleiteten Klasse erfolgen.</span><span class="sxs-lookup"><span data-stu-id="743c0-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="743c0-115">Die folgenden Beispiele veranschaulichen, wie Zugriffsmodifizierer für einen Typ und Member angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="743c0-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="743c0-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="743c0-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="743c0-117">Nicht alle Zugriffsmodifizierer können von allen Typen oder Membern in allen Kontexten verwendet werden, und in einigen Fällen wird der Zugriff auf einen Typmember vom Zugriff auf den enthaltenden Typ eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="743c0-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="743c0-118">Die folgenden Abschnitte enthalten ausführlichere Informationen zu diesem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="743c0-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="743c0-119">Zugriff auf Klasse und Strukturen</span><span class="sxs-lookup"><span data-stu-id="743c0-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="743c0-120">Klassen und Strukturen, die innerhalb eines Namespace (mit anderen Worten, die nicht in anderen Klassen oder Strukturen geschachtelt sind) direkt deklariert werden, können entweder öffentlich oder intern sein.</span><span class="sxs-lookup"><span data-stu-id="743c0-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="743c0-121">Wenn kein Modifizierer angegeben ist, wird standardmäßig „internal“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="743c0-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="743c0-122">Strukturmember, einschließlich geschachtelter Klassen und Strukturen, können als öffentlich, intern oder privat deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="743c0-123">Klassenmember, einschließlich geschachtelter Klassen und Strukturen, können public, protected internal, protected, internal oder private sein.</span><span class="sxs-lookup"><span data-stu-id="743c0-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="743c0-124">Die Zugriffsebene für Klassenmember und Strukturmember, einschließlich geschachtelter Klassen und Strukturen, ist standardmäßig privat.</span><span class="sxs-lookup"><span data-stu-id="743c0-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="743c0-125">Auf private geschachtelte Typen kann nicht von außerhalb des enthaltenden Typs zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="743c0-126">Abgeleitete Klassen können keine höhere Verfügbarkeit als ihre Basistypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="743c0-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="743c0-127">Das heißt, dass Sie über keine öffentliche Klasse `B` verfügen können, die von einer internen Klasse `A` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="743c0-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="743c0-128">Wenn dies zulässig wäre, müssten Sie `A` öffentlich machen, da auf alle geschützten oder internen Member von `A` aus der abgeleiteten Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="743c0-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="743c0-129">Sie können mithilfe des InternalsVisibleTo-Attributs bestimmten anderen Assemblys den Zugriff auf die internen Typen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="743c0-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="743c0-130">Weitere Informationen finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="743c0-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="743c0-131">Zugriff auf Klassen- und Strukturmember</span><span class="sxs-lookup"><span data-stu-id="743c0-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="743c0-132">Klassenmember (einschließlich geschachtelter Klassen und Strukturen) können mit einem der fünf Zugriffstypen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="743c0-133">Strukturmember können nicht als geschützt deklariert werden, da Strukturen keine Vererbung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="743c0-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="743c0-134">Normalerweise ist der Zugriff auf einen Member nicht höher als der Zugriff des Typs, der ihn enthält.</span><span class="sxs-lookup"><span data-stu-id="743c0-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="743c0-135">Allerdings kann auf einen öffentlichen Member einer internen Klasse möglicherweise von außerhalb der Assembly zugegriffen werden, wenn der Member Schnittstellenmethoden implementiert oder virtuelle Methoden überschreibt, die in einer öffentlichen Basisklasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="743c0-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="743c0-136">Der Typ jedes Members, der ein Feld, eine Eigenschaft oder ein Ereignis ist, muss mindestens über dieselben Zugriffstypen verfügen wie der Member selbst.</span><span class="sxs-lookup"><span data-stu-id="743c0-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="743c0-137">Ebenso müssen der Rückgabetyp und die Parametertypen eines Members, der eine Methode, Indexer oder Delegat ist, mindestens über dieselben Zugriffstypen verfügen, wie der Member selbst.</span><span class="sxs-lookup"><span data-stu-id="743c0-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="743c0-138">Zum Beispiel können Sie nicht über eine öffentliche Methode `M` verfügen, die eine Klasse `C` zurückgibt, außer wenn `C` ebenfalls öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="743c0-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="743c0-139">Ebenso können Sie nicht über eine geschützte Eigenschaft des Typs `A` verfügen, wenn `A` als privat deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="743c0-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="743c0-140">Benutzerdefinierte Operatoren müssen immer als öffentlich deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="743c0-141">Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="743c0-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="743c0-142">Finalizer können nicht über Zugriffsmodifizierer verfügen.</span><span class="sxs-lookup"><span data-stu-id="743c0-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="743c0-143">Um die Zugriffsebene für eine Klasse oder Struktur festzulegen, fügen Sie das entsprechende Schlüsselwort zur Memberdeklaration hinzu, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="743c0-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="743c0-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="743c0-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="743c0-145">Die geschützte interne Zugriffsebene heißt geschützt ODER intern, nicht geschützt UND intern.</span><span class="sxs-lookup"><span data-stu-id="743c0-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="743c0-146">Anders gesagt, kann auf einen geschützten internen Member aus einer Klasse in der gleichen Assembly, einschließlich der abgeleiteten Klassen, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="743c0-147">Um Zugriff auf abgeleitete Klassen in derselben Assembly zu beschränken, deklarieren Sie die Klasse selbst als intern, und ihre Member als geschützt.</span><span class="sxs-lookup"><span data-stu-id="743c0-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="743c0-148">Andere Typen</span><span class="sxs-lookup"><span data-stu-id="743c0-148">Other Types</span></span>  
 <span data-ttu-id="743c0-149">Schnittstellen, die direkt innerhalb eines Namespace deklariert werden, können als öffentlich oder intern deklariert werden, und haben wie Klassen und Strukturen standardmäßig internen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="743c0-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="743c0-150">Schnittstellenmember sind immer öffentlich, da es der Zweck einer Schnittstelle ist, anderen Typen den Zugriff auf eine Klasse oder Struktur zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="743c0-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="743c0-151">Auf Schnittstellenmember können keine Zugriffsmodifizierer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="743c0-152">Enumerationsmember sind immer öffentlich, und es können keine Zugriffsmodifizierer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="743c0-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="743c0-153">Delegaten verhalten sich wie Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="743c0-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="743c0-154">Standardmäßig haben sie internen Zugriff, wenn Sie direkt innerhalb eines Namespace deklariert werden, und privaten Zugriff bei Schachtelung.</span><span class="sxs-lookup"><span data-stu-id="743c0-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="743c0-155">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="743c0-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="743c0-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="743c0-156">See Also</span></span>  
 <span data-ttu-id="743c0-157">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="743c0-158">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="743c0-159">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="743c0-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="743c0-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="743c0-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="743c0-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="743c0-164">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="743c0-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="743c0-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="743c0-166">interface</span><span class="sxs-lookup"><span data-stu-id="743c0-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

