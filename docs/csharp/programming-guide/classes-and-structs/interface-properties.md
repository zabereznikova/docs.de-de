---
title: Schnittstelleneigenschaften (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
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
ms.openlocfilehash: 2b76cdc4e8419b08dcd95c3711eaead5513ae1d9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="f42a7-102">Schnittstelleneigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f42a7-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="f42a7-103">Eigenschaften können für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f42a7-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="f42a7-104">Das folgende Beispiel zeigt den Accessor für einen Schnittstellenindexer:</span><span class="sxs-lookup"><span data-stu-id="f42a7-104">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="f42a7-105">[!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f42a7-105">[!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]</span></span>  
  
 <span data-ttu-id="f42a7-106">Der Accessor einer Schnittstelleneigenschaft enthält keinen Text.</span><span class="sxs-lookup"><span data-stu-id="f42a7-106">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="f42a7-107">Der Zweck eines Accessors besteht darin anzugeben, ob die Eigenschaft gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.</span><span class="sxs-lookup"><span data-stu-id="f42a7-107">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42a7-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f42a7-108">Example</span></span>  
 <span data-ttu-id="f42a7-109">In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`.</span><span class="sxs-lookup"><span data-stu-id="f42a7-109">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="f42a7-110">Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f42a7-110">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="f42a7-111">Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f42a7-111">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="f42a7-112">Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="f42a7-112">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="f42a7-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f42a7-113">For example:</span></span>  
  
 <span data-ttu-id="f42a7-114">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f42a7-114">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="f42a7-115">Dies wird [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) genannt.</span><span class="sxs-lookup"><span data-stu-id="f42a7-115">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="f42a7-116">Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f42a7-116">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="f42a7-117">Das bedeutet, dass die folgende Eigenschaftendeklaration:</span><span class="sxs-lookup"><span data-stu-id="f42a7-117">That is, the following property declaration:</span></span>  
  
 <span data-ttu-id="f42a7-118">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f42a7-118">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="f42a7-119">die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="f42a7-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 <span data-ttu-id="f42a7-120">[!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f42a7-120">[!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="f42a7-121">die Eigenschaft `Name` für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="f42a7-121">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 <span data-ttu-id="f42a7-122">[!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f42a7-122">[!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]</span></span>  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="f42a7-123">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="f42a7-123">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="f42a7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f42a7-124">See Also</span></span>  
 <span data-ttu-id="f42a7-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f42a7-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f42a7-126">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="f42a7-126">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="f42a7-127">[Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f42a7-127">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="f42a7-128">[Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="f42a7-128">[Comparison Between Properties and Indexers](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md) </span></span>  
 <span data-ttu-id="f42a7-129">[Indexer](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="f42a7-129">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="f42a7-130">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f42a7-130">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

