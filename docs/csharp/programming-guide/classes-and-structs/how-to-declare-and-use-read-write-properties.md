---
title: 'Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften – C#-Programmierhandbuch'
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 4b9db5f15746ab9a1f42239150c6783154723371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170285"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="9be54-102">Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9be54-102">How to declare and use read write properties (C# Programming Guide)</span></span>
<span data-ttu-id="9be54-103">Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9be54-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="9be54-104">Dies wird durch *Accessoren* erreicht: Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="9be54-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="9be54-105">Der [set](../../language-reference/keywords/set.md)-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../language-reference/keywords/get.md)-Accessor ruft Datenmemberwerte ab.</span><span class="sxs-lookup"><span data-stu-id="9be54-105">The [set](../../language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="9be54-106">In diesem Beispiel wird eine `Person`-Klasse mit zwei Eigenschaften dargestellt: `Name` (Zeichenfolge) und `Age` (ganze Zahl).</span><span class="sxs-lookup"><span data-stu-id="9be54-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="9be54-107">Beide Eigenschaften stellen einen `get`- und einen `set`-Accessor bereit, es handelt sich also um Lese- bzw. Schreibeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9be54-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9be54-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9be54-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9be54-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="9be54-109">Robust Programming</span></span>  
 <span data-ttu-id="9be54-110">Im vorherigen Beispiel sind die `Name`- und `Age`-Eigenschaften [public (öffentlich)](../../language-reference/keywords/public.md) und besitzen jeweils einen `get`- und einen `set`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="9be54-110">In the previous example, the `Name` and `Age` properties are [public](../../language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="9be54-111">Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9be54-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="9be54-112">Manchmal ist es jedoch wünschenswert, einen der Accessoren auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="9be54-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="9be54-113">Indem Sie den `set`-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:</span><span class="sxs-lookup"><span data-stu-id="9be54-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="9be54-114">Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9be54-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="9be54-115">Weitere Informationen finden Sie unter [Asymmetric Accessor Accessibility (Asymmetrischer Accessorzugriff)](./restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="9be54-115">For more information, see [Asymmetric Accessor Accessibility](./restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="9be54-116">Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9be54-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="9be54-117">Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="9be54-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="9be54-118">Beachten Sie, dass in der `set`-Methode einer Eigenschaft eine spezielle `value`-Variable verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9be54-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="9be54-119">Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9be54-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="9be54-120">Beachten Sie die einfache Syntax zum Erhöhen des `Age`-Eigenschaftswerts eines `Person`-Objekts:</span><span class="sxs-lookup"><span data-stu-id="9be54-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="9be54-121">Wenn getrennte `set`- und `get`-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="9be54-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 <span data-ttu-id="9be54-122">Die `ToString`-Methode wird in diesem Beispiel überschrieben:</span><span class="sxs-lookup"><span data-stu-id="9be54-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="9be54-123">Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9be54-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="9be54-124">Es wird standardmäßig durch die `WriteLine`-Aufrufe aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9be54-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be54-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9be54-125">See also</span></span>

- [<span data-ttu-id="9be54-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9be54-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9be54-127">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9be54-127">Properties</span></span>](./properties.md)
- [<span data-ttu-id="9be54-128">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="9be54-128">Classes and Structs</span></span>](./index.md)
