---
title: Schnittstelleneigenschaften – C#-Programmierhandbuch
description: Eigenschaften können für eine Schnittstelle in C# deklariert werden. In diesem Beispiel wird eine Zugriffsmethode für Schnittstelleneigenschaften deklariert.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864968"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="29cc3-104">Schnittstelleneigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="29cc3-104">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="29cc3-105">Eigenschaften können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="29cc3-105">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="29cc3-106">Im folgenden Beispiel wird eine Zugriffsmethode für Schnittstelleneigenschaften deklariert:</span><span class="sxs-lookup"><span data-stu-id="29cc3-106">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="29cc3-107">Schnittstelleneigenschaften verfügen in der Regel über keinen Text.</span><span class="sxs-lookup"><span data-stu-id="29cc3-107">Interface properties typically don't have a body.</span></span> <span data-ttu-id="29cc3-108">Die Zugriffsmethoden geben an, ob Lese-/Schreibzugriff auf die Eigenschaft besteht oder ob sie schreib- oder lesegeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="29cc3-108">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="29cc3-109">Anders als bei Klassen und Strukturen wird beim Deklarieren von Zugriffsmethoden ohne Text keine [automatisch implementierte Eigenschaft](auto-implemented-properties.md) deklariert.</span><span class="sxs-lookup"><span data-stu-id="29cc3-109">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="29cc3-110">Ab C# 8.0 kann eine Schnittstelle eine Standardimplementierung für Member, einschließlich Eigenschaften, definieren.</span><span class="sxs-lookup"><span data-stu-id="29cc3-110">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="29cc3-111">Standardimplementierungen für Eigenschaften in einer Schnittstelle sind selten, weil Schnittstellen möglicherweise keine Instanzdatenfelder definieren.</span><span class="sxs-lookup"><span data-stu-id="29cc3-111">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="29cc3-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29cc3-112">Example</span></span>

<span data-ttu-id="29cc3-113">In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`.</span><span class="sxs-lookup"><span data-stu-id="29cc3-113">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="29cc3-114">Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="29cc3-114">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="29cc3-115">Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29cc3-115">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="29cc3-116">Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="29cc3-116">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="29cc3-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="29cc3-117">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="29cc3-118">Im vorangehenden Beispiel wird die [Explizite Schnittstellenimplementierung](../interfaces/explicit-interface-implementation.md) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="29cc3-118">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="29cc3-119">Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="29cc3-119">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="29cc3-120">Das bedeutet, dass die folgende Eigenschaftendeklaration:</span><span class="sxs-lookup"><span data-stu-id="29cc3-120">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="29cc3-121">die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="29cc3-121">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="29cc3-122">die Eigenschaft `Name` für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="29cc3-122">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="29cc3-123">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="29cc3-123">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="29cc3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29cc3-124">See also</span></span>

- [<span data-ttu-id="29cc3-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="29cc3-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="29cc3-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29cc3-126">Properties</span></span>](./properties.md)
- [<span data-ttu-id="29cc3-127">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="29cc3-127">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="29cc3-128">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="29cc3-128">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="29cc3-129">Indexer</span><span class="sxs-lookup"><span data-stu-id="29cc3-129">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="29cc3-130">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="29cc3-130">Interfaces</span></span>](../interfaces/index.md)
