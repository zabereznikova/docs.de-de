---
title: Schnittstelleneigenschaften – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: ff892a35f4be6600c00bc0c72c2f789ef6eb4408
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705534"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="df214-102">Schnittstelleneigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="df214-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="df214-103">Eigenschaften können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="df214-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="df214-104">Das folgende Beispiel zeigt den Accessor einer Schnittstelleneigenschaft:</span><span class="sxs-lookup"><span data-stu-id="df214-104">The following is an example of an interface property accessor:</span></span>

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

<span data-ttu-id="df214-105">Der Accessor einer Schnittstelleneigenschaft enthält keinen Text.</span><span class="sxs-lookup"><span data-stu-id="df214-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="df214-106">Der Zweck eines Accessors besteht darin anzugeben, ob die Eigenschaft gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.</span><span class="sxs-lookup"><span data-stu-id="df214-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>

## <a name="example"></a><span data-ttu-id="df214-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df214-107">Example</span></span>

<span data-ttu-id="df214-108">In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`.</span><span class="sxs-lookup"><span data-stu-id="df214-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="df214-109">Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="df214-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="df214-110">Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df214-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="df214-111">Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="df214-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="df214-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df214-112">For example:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="df214-113">Dies wird [Explizite Schnittstellenimplementierung](../interfaces/explicit-interface-implementation.md) genannt.</span><span class="sxs-lookup"><span data-stu-id="df214-113">This is called [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="df214-114">Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df214-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="df214-115">Das bedeutet, dass die folgende Eigenschaftendeklaration:</span><span class="sxs-lookup"><span data-stu-id="df214-115">That is, the following property declaration:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="df214-116">die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="df214-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

<span data-ttu-id="df214-117">die Eigenschaft `Name` für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="df214-117">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="df214-118">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="df214-118">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="df214-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df214-119">See also</span></span>

- [<span data-ttu-id="df214-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="df214-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="df214-121">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="df214-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="df214-122">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="df214-122">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="df214-123">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="df214-123">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="df214-124">Indexer</span><span class="sxs-lookup"><span data-stu-id="df214-124">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="df214-125">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="df214-125">Interfaces</span></span>](../interfaces/index.md)
