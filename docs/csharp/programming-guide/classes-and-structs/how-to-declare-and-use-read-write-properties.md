---
title: 'Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: d6a7083e1c0cf0dc5c076a69dee15fc39e234d53
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172318"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="5c862-102">Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5c862-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="5c862-103">Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5c862-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="5c862-104">Dies wird durch *Accessoren* erreicht: Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="5c862-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="5c862-105">Der [set](../../../csharp/language-reference/keywords/set.md)-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../../csharp/language-reference/keywords/get.md)-Accessor ruft Datenmemberwerte ab.</span><span class="sxs-lookup"><span data-stu-id="5c862-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="5c862-106">In diesem Beispiel wird eine `Person`-Klasse mit zwei Eigenschaften dargestellt: `Name` (Zeichenfolge) und `Age` (ganze Zahl).</span><span class="sxs-lookup"><span data-stu-id="5c862-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="5c862-107">Beide Eigenschaften stellen einen `get`- und einen `set`-Accessor bereit, es handelt sich also um Lese- bzw. Schreibeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5c862-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c862-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c862-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="5c862-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="5c862-109">Robust Programming</span></span>  
 <span data-ttu-id="5c862-110">Im vorherigen Beispiel sind die `Name`- und `Age`-Eigenschaften [public (öffentlich)](../../../csharp/language-reference/keywords/public.md) und besitzen jeweils einen `get`- und einen `set`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="5c862-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="5c862-111">Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5c862-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="5c862-112">Manchmal ist es jedoch wünschenswert, einen der Accessoren auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="5c862-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="5c862-113">Indem Sie den `set`-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:</span><span class="sxs-lookup"><span data-stu-id="5c862-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 <span data-ttu-id="5c862-114">Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5c862-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="5c862-115">Weitere Informationen finden Sie unter [Asymmetric Accessor Accessibility (Asymmetrischer Accessorzugriff)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="5c862-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="5c862-116">Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c862-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="5c862-117">Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="5c862-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 <span data-ttu-id="5c862-118">Beachten Sie, dass in der `set`-Methode einer Eigenschaft eine spezielle `value`-Variable verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5c862-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="5c862-119">Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5c862-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 <span data-ttu-id="5c862-120">Beachten Sie die einfache Syntax zum Erhöhen des `Age`-Eigenschaftswerts eines `Person`-Objekts:</span><span class="sxs-lookup"><span data-stu-id="5c862-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 <span data-ttu-id="5c862-121">Wenn getrennte `set`- und `get`-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="5c862-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="5c862-122">Die `ToString`-Methode wird in diesem Beispiel überschrieben:</span><span class="sxs-lookup"><span data-stu-id="5c862-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 <span data-ttu-id="5c862-123">Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c862-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="5c862-124">Es wird standardmäßig durch die `WriteLine`-Aufrufe aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5c862-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c862-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c862-125">See Also</span></span>  
 [<span data-ttu-id="5c862-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5c862-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5c862-127">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5c862-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="5c862-128">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="5c862-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
