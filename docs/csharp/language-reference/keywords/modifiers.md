---
title: Modifizierer (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- keywords [C#], modifiers
- modifiers [C#]
ms.assetid: c96691dd-b357-49ec-b5ae-03ca214fadfb
caps.latest.revision: 18
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
ms.openlocfilehash: 9e2e7e5e3907ac9bb66676e749ddd55a8ac4836c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="modifiers-c-reference"></a><span data-ttu-id="ebed9-102">Modifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ebed9-102">Modifiers (C# Reference)</span></span>
<span data-ttu-id="ebed9-103">Modifizierer werden zum Ändern von Typ- und Typmemberdeklarationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebed9-103">Modifiers are used to modify declarations of types and type members.</span></span> <span data-ttu-id="ebed9-104">In diesem Abschnitt werden die C#-Modifizierer beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebed9-104">This section introduces the C# modifiers.</span></span>  
  
|<span data-ttu-id="ebed9-105">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ebed9-105">Modifier</span></span>|<span data-ttu-id="ebed9-106">Zweck</span><span class="sxs-lookup"><span data-stu-id="ebed9-106">Purpose</span></span>|  
|--------------|-------------|  
|[<span data-ttu-id="ebed9-107">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="ebed9-107">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)<br /><br /> <span data-ttu-id="ebed9-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span><span class="sxs-lookup"><span data-stu-id="ebed9-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span></span><br /><span data-ttu-id="ebed9-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span><span class="sxs-lookup"><span data-stu-id="ebed9-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span></span><br /><span data-ttu-id="ebed9-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span><span class="sxs-lookup"><span data-stu-id="ebed9-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span></span><br /><span data-ttu-id="ebed9-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span><span class="sxs-lookup"><span data-stu-id="ebed9-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span></span>|<span data-ttu-id="ebed9-112">Gibt den deklarierten Zugriff von Typen und Typmembern an.</span><span class="sxs-lookup"><span data-stu-id="ebed9-112">Specifies the declared accessibility of types and type members.</span></span>|  
|[<span data-ttu-id="ebed9-113">abstract</span><span class="sxs-lookup"><span data-stu-id="ebed9-113">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="ebed9-114">Zeigt an, dass eine Klasse lediglich als Basisklasse anderer Klassen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ebed9-114">Indicates that a class is intended only to be a base class of other classes.</span></span>|  
|[<span data-ttu-id="ebed9-115">async</span><span class="sxs-lookup"><span data-stu-id="ebed9-115">async</span></span>](../../../csharp/language-reference/keywords/async.md)|<span data-ttu-id="ebed9-116">Zeigt an, dass die geänderte Methode, der Lambdaausdruck oder die anonyme Methode asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="ebed9-116">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="ebed9-117">const</span><span class="sxs-lookup"><span data-stu-id="ebed9-117">const</span></span>](../../../csharp/language-reference/keywords/const.md)|<span data-ttu-id="ebed9-118">Gibt an, dass der Wert des Felds oder der lokalen Variablen nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebed9-118">Specifies that the value of the field or the local variable cannot be modified.</span></span>|  
|[<span data-ttu-id="ebed9-119">event</span><span class="sxs-lookup"><span data-stu-id="ebed9-119">event</span></span>](../../../csharp/language-reference/keywords/event.md)|<span data-ttu-id="ebed9-120">Deklariert ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ebed9-120">Declares an event.</span></span>|  
|[<span data-ttu-id="ebed9-121">extern</span><span class="sxs-lookup"><span data-stu-id="ebed9-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)|<span data-ttu-id="ebed9-122">Zeigt an, dass die Methode extern implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ebed9-122">Indicates that the method is implemented externally.</span></span>|  
|[<span data-ttu-id="ebed9-123">new</span><span class="sxs-lookup"><span data-stu-id="ebed9-123">new</span></span>](../../../csharp/language-reference/keywords/new.md)|<span data-ttu-id="ebed9-124">Blendet einen von einer Basisklasse geerbten Member explizit aus.</span><span class="sxs-lookup"><span data-stu-id="ebed9-124">Explicitly hides a member inherited from a base class.</span></span>|  
|[<span data-ttu-id="ebed9-125">override</span><span class="sxs-lookup"><span data-stu-id="ebed9-125">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="ebed9-126">Stellt eine neue Implementierung eines virtuellen Members bereit, der von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="ebed9-126">Provides a new implementation of a virtual member inherited from a base class.</span></span>|  
|[<span data-ttu-id="ebed9-127">partial</span><span class="sxs-lookup"><span data-stu-id="ebed9-127">partial</span></span>](../../../csharp/language-reference/keywords/partial-type.md)|<span data-ttu-id="ebed9-128">Definiert Teilklassen, Strukturen und Methoden innerhalb derselben Assembly.</span><span class="sxs-lookup"><span data-stu-id="ebed9-128">Defines partial classes, structs and methods throughout the same assembly.</span></span>|  
|[<span data-ttu-id="ebed9-129">readonly</span><span class="sxs-lookup"><span data-stu-id="ebed9-129">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)|<span data-ttu-id="ebed9-130">Deklariert ein Feld, dem Werte nur als Teil einer Deklaration oder in einem Konstruktor derselben Klasse zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="ebed9-130">Declares a field that can only be assigned values as part of the declaration or in a constructor in the same class.</span></span>|  
|[<span data-ttu-id="ebed9-131">sealed</span><span class="sxs-lookup"><span data-stu-id="ebed9-131">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="ebed9-132">Gibt an, dass eine Klasse nicht geerbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebed9-132">Specifies that a class cannot be inherited.</span></span>|  
|[<span data-ttu-id="ebed9-133">static</span><span class="sxs-lookup"><span data-stu-id="ebed9-133">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="ebed9-134">Deklariert einen Member, der zum Typ selbst und nicht zu einem bestimmten Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="ebed9-134">Declares a member that belongs to the type itself instead of to a specific object.</span></span>|  
|[<span data-ttu-id="ebed9-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="ebed9-135">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)|<span data-ttu-id="ebed9-136">Deklariert einen nicht sicheren Kontext.</span><span class="sxs-lookup"><span data-stu-id="ebed9-136">Declares an unsafe context.</span></span>|  
|[<span data-ttu-id="ebed9-137">virtual</span><span class="sxs-lookup"><span data-stu-id="ebed9-137">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="ebed9-138">Deklariert eine Methode oder eine Zugriffsmethode, deren Implementierung durch einen überschreibenden Member in einer abgeleiteten Klasse geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebed9-138">Declares a method or an accessor whose implementation can be changed by an overriding member in a derived class.</span></span>|  
|[<span data-ttu-id="ebed9-139">volatile</span><span class="sxs-lookup"><span data-stu-id="ebed9-139">volatile</span></span>](../../../csharp/language-reference/keywords/volatile.md)|<span data-ttu-id="ebed9-140">Gibt an, dass ein Feld im Programm z. B. vom Betriebssystem, der Hardware oder einem gleichzeitig ausgeführten Thread geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebed9-140">Indicates that a field can be modified in the program by something such as the operating system, the hardware, or a concurrently executing thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebed9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebed9-141">See Also</span></span>  
 <span data-ttu-id="ebed9-142">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ebed9-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ebed9-143">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ebed9-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ebed9-144">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ebed9-144">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

