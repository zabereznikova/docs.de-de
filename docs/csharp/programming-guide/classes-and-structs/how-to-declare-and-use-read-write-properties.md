---
title: 'Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5e4ca1feff203dc2ab88c0d1dfae8098508fec7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="c0f55-102">Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c0f55-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="c0f55-103">Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c0f55-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="c0f55-104">Dies wird durch *Accessoren* erreicht: Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="c0f55-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="c0f55-105">Der [set](../../../csharp/language-reference/keywords/set.md)-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../../csharp/language-reference/keywords/get.md)-Accessor ruft Datenmemberwerte ab.</span><span class="sxs-lookup"><span data-stu-id="c0f55-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="c0f55-106">In diesem Beispiel wird eine `Person`-Klasse mit zwei Eigenschaften dargestellt: `Name` (Zeichenfolge) und `Age` (ganze Zahl).</span><span class="sxs-lookup"><span data-stu-id="c0f55-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="c0f55-107">Beide Eigenschaften stellen einen `get`- und einen `set`-Accessor bereit, es handelt sich also um Lese- bzw. Schreibeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c0f55-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f55-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0f55-108">Example</span></span>  
 <span data-ttu-id="c0f55-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c0f55-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c0f55-110">Robust Programming</span></span>  
 <span data-ttu-id="c0f55-111">Im vorherigen Beispiel sind die `Name`- und `Age`-Eigenschaften [public (öffentlich)](../../../csharp/language-reference/keywords/public.md) und besitzen jeweils einen `get`- und einen `set`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="c0f55-111">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="c0f55-112">Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c0f55-112">This allows any object to read and write these properties.</span></span> <span data-ttu-id="c0f55-113">Manchmal ist es jedoch wünschenswert, einen der Accessoren auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="c0f55-113">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="c0f55-114">Indem Sie den `set`-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:</span><span class="sxs-lookup"><span data-stu-id="c0f55-114">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 <span data-ttu-id="c0f55-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="c0f55-116">Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c0f55-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="c0f55-117">Weitere Informationen finden Sie unter [Asymmetric Accessor Accessibility (Asymmetrischer Accessorzugriff)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="c0f55-117">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="c0f55-118">Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0f55-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="c0f55-119">Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="c0f55-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 <span data-ttu-id="c0f55-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="c0f55-121">Beachten Sie, dass in der `set`-Methode einer Eigenschaft eine spezielle `value`-Variable verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c0f55-121">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="c0f55-122">Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c0f55-122">This variable contains the value that the user specified, for example:</span></span>  
  
 <span data-ttu-id="c0f55-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span></span>  
  
 <span data-ttu-id="c0f55-124">Beachten Sie die einfache Syntax zum Erhöhen des `Age`-Eigenschaftswerts eines `Person`-Objekts:</span><span class="sxs-lookup"><span data-stu-id="c0f55-124">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 <span data-ttu-id="c0f55-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span></span>  
  
 <span data-ttu-id="c0f55-126">Wenn getrennte `set`- und `get`-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="c0f55-126">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="c0f55-127">Die `ToString`-Methode wird in diesem Beispiel überschrieben:</span><span class="sxs-lookup"><span data-stu-id="c0f55-127">The `ToString` method is overridden in this example:</span></span>  
  
 <span data-ttu-id="c0f55-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0f55-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span></span>  
  
 <span data-ttu-id="c0f55-129">Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0f55-129">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="c0f55-130">Es wird standardmäßig durch die `WriteLine`-Aufrufe aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c0f55-130">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f55-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f55-131">See Also</span></span>  
 <span data-ttu-id="c0f55-132">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0f55-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c0f55-133">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="c0f55-133">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="c0f55-134">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="c0f55-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

