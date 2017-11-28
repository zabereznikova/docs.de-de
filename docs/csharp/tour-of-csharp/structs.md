---
title: "C#-Strukturen – Überblick über C#"
description: Lernen Sie die Grundlagen der als Strukturen bezeichneten C#-Werttypen kennen.
keywords: .NET, C#, Struktur, Werttyp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: 9d435fd87a6103d505c14219499eeea9aee045fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="structs"></a><span data-ttu-id="90071-104">Strukturen</span><span class="sxs-lookup"><span data-stu-id="90071-104">Structs</span></span>

<span data-ttu-id="90071-105">Wie Klassen sind ***Strukturen*** Datenstrukturen, die Datenmember und Funktionsmember enthalten können, aber im Gegensatz zu Klassen sind Strukturen Werttypen und erfordern keine Heapzuordnung.</span><span class="sxs-lookup"><span data-stu-id="90071-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="90071-106">Eine Variable eines Strukturtyps speichert die Daten der Struktur direkt, während eine Variable eines Klassentyps einen Verweis auf ein dynamisch zugeordnetes Objekt speichert.</span><span class="sxs-lookup"><span data-stu-id="90071-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="90071-107">Strukturtypen unterstützen keine benutzerdefinierte Vererbung, und alle Strukturtypen erben implizit vom Typ <xref:System.ValueType>, der wiederum implizit von `object` erbt.</span><span class="sxs-lookup"><span data-stu-id="90071-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="90071-108">Strukturen sind besonders nützlich für kleine Datenstrukturen, die über Wertsemantik verfügen.</span><span class="sxs-lookup"><span data-stu-id="90071-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="90071-109">Komplexe Zahlen, Punkte in einem Koordinatensystem oder Schlüssel-Wert-Paare im Wörterbuch sind gute Beispiele für Strukturen.</span><span class="sxs-lookup"><span data-stu-id="90071-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="90071-110">Die Verwendung von Strukturen statt Klassen für kleine Datenstrukturen kann bei der Anzahl der Speicherbelegungen, die eine Anwendung durchführt, einen großen Unterschied ausmachen.</span><span class="sxs-lookup"><span data-stu-id="90071-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="90071-111">Das folgende Programm erstellt und initialisiert z.B. ein Array aus 100 Punkten.</span><span class="sxs-lookup"><span data-stu-id="90071-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="90071-112">Mit `Point` als implementierter Klasse werden 101 separate Objekte instanziiert – eines für das Array und jeweils eines für jedes der 100 Elemente.</span><span class="sxs-lookup"><span data-stu-id="90071-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

<span data-ttu-id="90071-113">Eine Alternative ist, „Point“ zu einer Struktur zu machen.</span><span class="sxs-lookup"><span data-stu-id="90071-113">An alternative is to make Point a struct.</span></span>

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

<span data-ttu-id="90071-114">Jetzt wird nur ein Objekt instanziiert – für das Array – und die `Point`-Instanzen werden inline im Array gespeichert.</span><span class="sxs-lookup"><span data-stu-id="90071-114">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="90071-115">Strukturkonstruktoren werden mit dem neuen Operator aufgerufen, doch das bedeutet nicht, dass der Arbeitsspeicher belegt wird.</span><span class="sxs-lookup"><span data-stu-id="90071-115">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="90071-116">Statt ein Objekt dynamisch zuzuordnen und einen Verweis darauf zurückzugeben, gibt ein Strukturkonstruktor einfach den Strukturwert selbst zurück (in der Regel in einen temporären Speicherort auf dem Stapel), und dieser Wert wird dann nach Bedarf kopiert.</span><span class="sxs-lookup"><span data-stu-id="90071-116">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="90071-117">Mit Klassen können zwei Variablen auf das gleiche Objekt verweisen, und so können an einer Variablen durchgeführte Vorgänge das Objekt beeinflussen, auf das die andere Variable verweist.</span><span class="sxs-lookup"><span data-stu-id="90071-117">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="90071-118">Mit Strukturen besitzt jede Variable eine eigene Kopie der Daten, und es ist nicht möglich, dass an einer Variablen durchgeführte Vorgänge die andere beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="90071-118">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="90071-119">Welche Ausgabe das folgende Codefragment erzeugt, hängt beispielsweise davon ab, ob „Point“ eine Klasse oder eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="90071-119">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

<span data-ttu-id="90071-120">Wenn `Point` eine Klasse ist, ist die Ausgabe 20, da „a“ und „b“ auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="90071-120">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="90071-121">Wenn „Point“ eine Struktur ist, ist die Ausgabe 10, da die Zuweisung von `a` zu `b` eine Kopie des Werts erstellt, und diese Kopie ist nicht von der nachfolgenden Zuweisung zu `a.x` betroffen.</span><span class="sxs-lookup"><span data-stu-id="90071-121">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="90071-122">Im vorherigen Beispiel werden zwei der Einschränkungen von Strukturen hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="90071-122">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="90071-123">Erstens ist das Kopieren einer gesamten Struktur in der Regel weniger effizient als das Kopieren eines Objektverweises, sodass Zuweisung und Wertparameterübergabe mit Strukturen aufwändiger sein kann als mit Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="90071-123">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="90071-124">Zweitens ist es mit Ausnahme der `ref`- und `out`-Parameter nicht möglich, Verweise auf Strukturen zu erstellen, was ihre Verwendung in einer Reihe von Situationen ausschließt.</span><span class="sxs-lookup"><span data-stu-id="90071-124">Second, except for `ref` and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="90071-125">[Zurück](classes-and-objects.md)
[Weiter](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="90071-125">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>
