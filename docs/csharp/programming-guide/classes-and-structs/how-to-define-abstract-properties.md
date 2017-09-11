---
title: 'Gewusst wie: Definieren von abstrakten Eigenschaften (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
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
ms.openlocfilehash: c6decaae138a21c24e94e2ed74111c860777f64b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="b29af-102">Gewusst wie: Definieren von abstrakten Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b29af-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="b29af-103">Das folgende Beispiel veranschaulicht, wie Sie [abstrakte](../../../csharp/language-reference/keywords/abstract.md) Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="b29af-103">The following example shows how to define [abstract](../../../csharp/language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="b29af-104">Eine abstrakte Eigenschaftendeklaration stellt keine Implementierung des Eigenschaftenaccessors bereit, sondern deklariert, dass die Klasse Eigenschaften unterstützt, die Accessorenimplementierung jedoch abgeleiteten Klassen überlässt.</span><span class="sxs-lookup"><span data-stu-id="b29af-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="b29af-105">Das folgende Beispiel veranschaulicht das Implementieren von abstrakten Eigenschaften, die von einer Basisklasse geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="b29af-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="b29af-106">Dieses Beispiel besteht aus drei Dateien, von denen jede einzeln kompiliert wird, und auf die daraus entstehende Assembly von der nächsten Kompilierung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b29af-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
-   <span data-ttu-id="b29af-107">abstractshape.cs: die `Shape`-Klasse, die eine abstrakte `Area`-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="b29af-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
-   <span data-ttu-id="b29af-108">shapes.cs: die Unterklassen der `Shape`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b29af-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
-   <span data-ttu-id="b29af-109">shapetest.cs: ein Testprogramm zum Anzeigen der Bereiche einiger abgeleiteten `Shape`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="b29af-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="b29af-110">Verwenden Sie den folgenden Befehl, um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="b29af-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="b29af-111">Dadurch wird die ausführbare Datei „shapetest.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="b29af-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29af-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b29af-112">Example</span></span>  
 <span data-ttu-id="b29af-113">Diese Datei deklariert die `Shape`-Klasse, die die `Area`-Eigenschaft des Typs `double` enthält.</span><span class="sxs-lookup"><span data-stu-id="b29af-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 <span data-ttu-id="b29af-114">[!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b29af-114">[!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]</span></span>  
  
-   <span data-ttu-id="b29af-115">Modifizierer der Eigenschaft sind in der Deklaration der Eigenschaft selbst platziert.</span><span class="sxs-lookup"><span data-stu-id="b29af-115">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="b29af-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b29af-116">For example:</span></span>  
  
    ```  
    public abstract double Area  
    ```  
  
-   <span data-ttu-id="b29af-117">Wenn Sie eine abstrakte Eigenschaft deklarieren (z.B. `Area` in diesem Beispiel), geben Sie lediglich an, welche Eigenschaftenaccessoren verfügbar sind, implementieren diese jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="b29af-117">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="b29af-118">In diesem Beispiel ist nur ein [get](../../../csharp/language-reference/keywords/get.md)-Accessor verfügbar, die Eigenschaft ist also schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b29af-118">In this example, only a [get](../../../csharp/language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29af-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b29af-119">Example</span></span>  
 <span data-ttu-id="b29af-120">Der folgende Code zeigt drei Unterklassen von `Shape` und wie sie die `Area`-Eigenschaft überschreiben, um ihre eigene Implementierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b29af-120">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 <span data-ttu-id="b29af-121">[!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b29af-121">[!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29af-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b29af-122">Example</span></span>  
 <span data-ttu-id="b29af-123">Der folgende Code zeigt ein Testprogramm, das eine Reihe abgeleiteter `Shape`-Objekte erstellt und deren Bereiche ausdruckt.</span><span class="sxs-lookup"><span data-stu-id="b29af-123">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 <span data-ttu-id="b29af-124">[!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b29af-124">[!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29af-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b29af-125">See Also</span></span>  
 <span data-ttu-id="b29af-126">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b29af-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b29af-127">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b29af-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="b29af-128">[Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="b29af-128">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="b29af-129">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="b29af-129">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="b29af-130">Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="b29af-130">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)

