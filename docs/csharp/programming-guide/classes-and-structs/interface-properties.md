---
title: Schnittstelleneigenschaften – C#-Programmierhandbuch
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626619"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="a9fa6-102">Schnittstelleneigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a9fa6-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="a9fa6-103">Eigenschaften können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="a9fa6-104">Im folgenden Beispiel wird eine Zugriffsmethode für Schnittstelleneigenschaften deklariert:</span><span class="sxs-lookup"><span data-stu-id="a9fa6-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="a9fa6-105">Schnittstelleneigenschaften verfügen in der Regel über keinen Text.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="a9fa6-106">Die Zugriffsmethoden geben an, ob Lese-/Schreibzugriff auf die Eigenschaft besteht oder ob sie schreib- oder lesegeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="a9fa6-107">Anders als bei Klassen und Strukturen wird beim Deklarieren von Zugriffsmethoden ohne Text keine [automatisch implementierte Eigenschaft](auto-implemented-properties.md) deklariert.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="a9fa6-108">Ab C# 8.0 kann eine Schnittstelle eine Standardimplementierung für Member, einschließlich Eigenschaften, definieren.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="a9fa6-109">Standardimplementierungen für Eigenschaften in einer Schnittstelle sind selten, weil Schnittstellen möglicherweise keine Instanzdatenfelder definieren.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="a9fa6-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9fa6-110">Example</span></span>

<span data-ttu-id="a9fa6-111">In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="a9fa6-112">Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="a9fa6-113">Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="a9fa6-114">Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="a9fa6-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9fa6-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="a9fa6-116">Im vorangehenden Beispiel wird die [Explizite Schnittstellenimplementierung](../interfaces/explicit-interface-implementation.md) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="a9fa6-117">Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="a9fa6-118">Das bedeutet, dass die folgende Eigenschaftendeklaration:</span><span class="sxs-lookup"><span data-stu-id="a9fa6-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="a9fa6-119">die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="a9fa6-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="a9fa6-120">die Eigenschaft `Name` für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="a9fa6-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="a9fa6-121">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="a9fa6-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="a9fa6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9fa6-122">See also</span></span>

- [<span data-ttu-id="a9fa6-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a9fa6-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a9fa6-124">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a9fa6-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="a9fa6-125">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a9fa6-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="a9fa6-126">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="a9fa6-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="a9fa6-127">Indexer</span><span class="sxs-lookup"><span data-stu-id="a9fa6-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="a9fa6-128">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9fa6-128">Interfaces</span></span>](../interfaces/index.md)
