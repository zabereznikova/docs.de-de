---
title: 'with-Ausdruck: C#-Referenz'
description: Hier erhalten Sie Informationen zu einem with-Ausdruck, der nicht destruktive Änderungen von C#-Datensätzen durchführt.
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: d7d3758c8c5da7859974b5b50b63d2a5ca16b24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702224"
---
# <a name="with-expression-c-reference"></a><span data-ttu-id="402d6-103">with-Ausdruck (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="402d6-103">with expression (C# reference)</span></span>

<span data-ttu-id="402d6-104">Ab C# 9.0 ist ein `with`-Ausdruck verfügbar, der eine Kopie des dazugehörigen [Datensatzoperanden](../../whats-new/csharp-9.md#record-types) mit den angegebenen Eigenschaften und bearbeiteten Feldern erzeugt:</span><span class="sxs-lookup"><span data-stu-id="402d6-104">Available in C# 9.0 and later, a `with` expression produces a copy of its [record](../../whats-new/csharp-9.md#record-types) operand with the specified properties and fields modified:</span></span>

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

<span data-ttu-id="402d6-105">Wie das vorherige Beispiel zeigt, verwenden Sie die [Objektinitialisierersyntax](../../programming-guide/classes-and-structs/object-and-collection-initializers.md), um anzugeben, welche Member bearbeitet und welche neuen Werte dazu verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="402d6-105">As the preceding example shows, you use [object initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) syntax to specify what members to modify and their new values.</span></span> <span data-ttu-id="402d6-106">In einem `with`-Ausdruck muss ein linker Operand den Typ „Datensatz“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="402d6-106">In a `with` expression, a left-hand operand must be of a record type.</span></span>

<span data-ttu-id="402d6-107">Das Ergebnis eines `with`-Ausdrucks weist denselben Runtimetyp auf wie der Operand des Ausdrucks. Sehen Sie sich dazu das folgende Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="402d6-107">The result of a `with` expression has the same runtime type as the expression's operand, as the following example shows:</span></span>

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

<span data-ttu-id="402d6-108">Wenn der Member einen Verweistyp aufweist, wird beim Kopieren eines Datensatzes nur der Verweis auf eine Instanz kopiert.</span><span class="sxs-lookup"><span data-stu-id="402d6-108">In the case of a reference-type member, only the reference to an instance is copied when a record is copied.</span></span> <span data-ttu-id="402d6-109">Sowohl der kopierte als auch der ursprüngliche Datensatz haben Zugriff auf dieselbe Verweistypinstanz.</span><span class="sxs-lookup"><span data-stu-id="402d6-109">Both the copy and original record have access to the same reference-type instance.</span></span> <span data-ttu-id="402d6-110">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="402d6-110">The following example demonstrates that behavior:</span></span>

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

<span data-ttu-id="402d6-111">Jeder Datensatztyp weist den *Kopierkonstruktor* auf.</span><span class="sxs-lookup"><span data-stu-id="402d6-111">Any record type has the *copy constructor*.</span></span> <span data-ttu-id="402d6-112">Dabei handelt es sich um einen Konstruktor mit einzelnem Parameter, der den Typ des Datensatzes aufweist, in dem er enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="402d6-112">That is a constructor with a single parameter of the containing record type.</span></span> <span data-ttu-id="402d6-113">Der Zustand des dazugehörigen Arguments wird in eine neue Datensatzinstanz kopiert.</span><span class="sxs-lookup"><span data-stu-id="402d6-113">It copies the state of its argument to a new record instance.</span></span> <span data-ttu-id="402d6-114">Wenn ein `with`-Ausdruck ausgewertet wird, wird der Kopierkonstruktor aufgerufen, um eine neue Datensatzinstanz basierend auf dem ursprünglichen Datensatz zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="402d6-114">At evaluation of a `with` expression, the copy constructor gets called to instantiate a new record instance based on an original record.</span></span> <span data-ttu-id="402d6-115">Danach wird die neue Instanz entsprechend der angegebenen Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="402d6-115">After that, the new instance gets updated according to the specified modifications.</span></span> <span data-ttu-id="402d6-116">Standardmäßig ist der Kopierkonstruktor implizit, das heißt, vom Compiler generiert.</span><span class="sxs-lookup"><span data-stu-id="402d6-116">By default, the copy constructor is implicit, that is, compiler-generated.</span></span> <span data-ttu-id="402d6-117">Wenn Sie die Kopiersemantik des Datensatzes anpassen möchten, deklarieren Sie explizit einen Kopierkonstruktor mit gewünschtem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="402d6-117">If you need to customize the record copy semantics, explicitly declare a copy constructor with the desired behavior.</span></span> <span data-ttu-id="402d6-118">Das folgende Beispiel aktualisiert das vorherige Beispiel mit einem expliziten Kopierkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="402d6-118">The following example updates the preceding example with an explicit copy constructor.</span></span> <span data-ttu-id="402d6-119">Das neue Kopierverhalten besteht darin, Listenelemente anstatt eines Listenverweises zu kopieren, wenn ein Datensatz kopiert wird:</span><span class="sxs-lookup"><span data-stu-id="402d6-119">The new copy behavior is to copy list items instead of a list reference when a record is copied:</span></span>

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a><span data-ttu-id="402d6-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="402d6-120">C# language specification</span></span>

<span data-ttu-id="402d6-121">Weitere Informationen finden Sie in den folgenden Abschnitten des Artikels [Datensätze](~/_csharplang/proposals/csharp-9.0/records.md):</span><span class="sxs-lookup"><span data-stu-id="402d6-121">For more information, see the following sections of the [records feature proposal note](~/_csharplang/proposals/csharp-9.0/records.md):</span></span>

- [<span data-ttu-id="402d6-122">`with`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="402d6-122">`with` expression</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [<span data-ttu-id="402d6-123">Methoden zum Kopieren und Klonen von Membern</span><span class="sxs-lookup"><span data-stu-id="402d6-123">Copy and Clone members</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a><span data-ttu-id="402d6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="402d6-124">See also</span></span>

- [<span data-ttu-id="402d6-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="402d6-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="402d6-126">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="402d6-126">C# operators and expressions</span></span>](index.md)
