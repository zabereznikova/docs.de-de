---
title: Indexer in Schnittstellen – C#-Programmierhandbuch
description: Indexer können in einer Schnittstelle in C# deklariert werden. Erfahren, wie Accessoren für Schnittstellenindexer sich von den Accessoren für Klassenindexer unterscheiden.
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: ec77843bdf3181a543bd6c02cfb034b21ded1ae7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303100"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="d4a79-104">Indexer in Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d4a79-104">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="d4a79-105">Indexer können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d4a79-105">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="d4a79-106">Accessoren für Schnittstellenindexer unterscheiden sich von den Accessoren für [Klassen](../../language-reference/keywords/class.md)-Indexer in den folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="d4a79-106">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="d4a79-107">Schnittstellenaccessoren verwenden keine Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d4a79-107">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="d4a79-108">Schnittstellenzugriffsmethoden weisen in der Regel keinen Text auf.</span><span class="sxs-lookup"><span data-stu-id="d4a79-108">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="d4a79-109">Der Zweck einer Zugriffsmethode besteht darin, anzugeben, ob der Indexer gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.</span><span class="sxs-lookup"><span data-stu-id="d4a79-109">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="d4a79-110">In seltenen Fällen müssen Sie eine Implementierung für einen in einer Schnittstelle definierten Indexer angeben.</span><span class="sxs-lookup"><span data-stu-id="d4a79-110">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="d4a79-111">Indexer definieren üblicherweise eine API für den Zugriff auf Datenfelder, und Datenfelder können nicht in einer Schnittstelle definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4a79-111">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="d4a79-112">Das folgende Beispiel zeigt den Accessor für einen Schnittstellenindexer:</span><span class="sxs-lookup"><span data-stu-id="d4a79-112">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="d4a79-113">Die Signatur eines Indexers muss sich von den Signaturen aller anderen in derselben Schnittstelle deklarierten Indexer unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d4a79-113">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="d4a79-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4a79-114">Example</span></span>

<span data-ttu-id="d4a79-115">Das folgende Beispiel zeigt, wie Schnittstellenindexer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4a79-115">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="d4a79-116">Im vorherigen Beispiel könnte der Schnittstellenmember durch Verwendung des vollqualifizierten Namens des Schnittstellenmembers explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4a79-116">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="d4a79-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a79-117">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="d4a79-118">Der vollqualifizierte Name ist jedoch nur erforderlich, um Mehrdeutigkeiten zu vermeiden, wenn mehr als eine Schnittstelle mit derselben Indexersignatur von der Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="d4a79-118">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="d4a79-119">Wenn z.B. eine `Employee`-Klasse die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen dieselbe Indexersignatur besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4a79-119">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="d4a79-120">Das bedeutet, dass die folgende Indexerdeklaration:</span><span class="sxs-lookup"><span data-stu-id="d4a79-120">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
```

<span data-ttu-id="d4a79-121">den Indexer für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="d4a79-121">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="d4a79-122">den Indexer für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="d4a79-122">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a79-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4a79-123">See also</span></span>

- [<span data-ttu-id="d4a79-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d4a79-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d4a79-125">Indexer</span><span class="sxs-lookup"><span data-stu-id="d4a79-125">Indexers</span></span>](./index.md)
- [<span data-ttu-id="d4a79-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4a79-126">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="d4a79-127">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4a79-127">Interfaces</span></span>](../interfaces/index.md)
