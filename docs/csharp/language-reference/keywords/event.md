---
title: event (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
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
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="af01e-102">event (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="af01e-102">event (C# Reference)</span></span>
<span data-ttu-id="af01e-103">Das `event`-Schlüsselwort wird verwendet, um ein Ereignis in einer Publisher-Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="af01e-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af01e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af01e-104">Example</span></span>  
 <span data-ttu-id="af01e-105">Das folgende Beispiel zeigt das Deklarieren und Auslösen eines Ereignisses, das <xref:System.EventHandler> als zugrunde liegenden Delegattyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="af01e-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="af01e-106">Für das vollständige Codebeispiel, das auch veranschaulicht, wie der generische Delegattyp <xref:System.EventHandler%601> verwendet wird und wie man ein Ereignis abonniert und eine Ereignishandlermethode erstellt, finden Sie unter [Vorgehensweise: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="af01e-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="af01e-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="af01e-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="af01e-108">Ereignisse sind eine besondere Art von Multicastdelegaten, die nur aus der Klasse oder Struktur, in der sie deklariert sind (Publisher-Klasse), aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="af01e-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="af01e-109">Wenn andere Klassen oder Strukturen das Ereignis abonnieren, werden ihre Ereignishandlermethoden aufgerufen werden, wenn die Publisher-Klasse das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="af01e-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="af01e-110">Weitere Informationen und Codebeispiele finden Sie unter [Ereignisse](../../../csharp/programming-guide/events/index.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="af01e-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="af01e-111">Ereignisse können markiert werden als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="af01e-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="af01e-112">Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf das Ereignis zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="af01e-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="af01e-113">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="af01e-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="af01e-114">Schlüsselwörter und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="af01e-114">Keywords and Events</span></span>  
 <span data-ttu-id="af01e-115">Die folgenden Schlüsselwörter gelten für Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="af01e-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="af01e-116">Stichwort</span><span class="sxs-lookup"><span data-stu-id="af01e-116">Keyword</span></span>|<span data-ttu-id="af01e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af01e-117">Description</span></span>|<span data-ttu-id="af01e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af01e-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="af01e-119">static</span><span class="sxs-lookup"><span data-stu-id="af01e-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="af01e-120">Stellt das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af01e-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="af01e-121">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="af01e-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="af01e-122">virtual</span><span class="sxs-lookup"><span data-stu-id="af01e-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="af01e-123">Ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](../../../csharp/language-reference/keywords/override.md)-Schlüsselworts zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="af01e-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="af01e-124">Vererbung</span><span class="sxs-lookup"><span data-stu-id="af01e-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="af01e-125">sealed</span><span class="sxs-lookup"><span data-stu-id="af01e-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="af01e-126">Gibt an, dass für abgeleitete Klassen „virtual“ nicht mehr gilt.</span><span class="sxs-lookup"><span data-stu-id="af01e-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="af01e-127">abstract</span><span class="sxs-lookup"><span data-stu-id="af01e-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="af01e-128">Der Compiler wird keine `add`- und `remove`-Ereignisaccessorblöcke generieren und daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="af01e-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="af01e-129">Ein Ereignis kann mithilfe des [static](../../../csharp/language-reference/keywords/static.md)-Schlüsselworts als statisches Ereignis deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="af01e-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="af01e-130">Dadurch steht das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af01e-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="af01e-131">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="af01e-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="af01e-132">Ein Ereignis kann mithilfe des [virtual](../../../csharp/language-reference/keywords/virtual.md)-Schlüsselworts als virtuelles Ereignis gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="af01e-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="af01e-133">Dies ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](../../../csharp/language-reference/keywords/override.md)-Schlüsselworts zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="af01e-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="af01e-134">Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="af01e-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="af01e-135">Ein Ereignis, das ein virtuelles Ereignis überschreibt, kann auch [sealed](../../../csharp/language-reference/keywords/sealed.md) sein, was angibt, dass für abgeleitete Klassen „virtual“ nicht mehr gilt.</span><span class="sxs-lookup"><span data-stu-id="af01e-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="af01e-136">Schließlich kann ein Ereignis als [abstract](../../../csharp/language-reference/keywords/abstract.md) deklariert werden, d.h., dass der Compiler die `add`- und `remove`-Ereignisaccessorblöcke nicht generieren wird.</span><span class="sxs-lookup"><span data-stu-id="af01e-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="af01e-137">Daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="af01e-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="af01e-138">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="af01e-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af01e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af01e-139">See Also</span></span>  
 <span data-ttu-id="af01e-140">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="af01e-141">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="af01e-142">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="af01e-143">[add](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="af01e-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="af01e-145">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="af01e-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="af01e-146">Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten)</span><span class="sxs-lookup"><span data-stu-id="af01e-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

