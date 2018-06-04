---
title: Neues in C# 7.2
description: Eine Übersicht der neuen Funktionen in C# 7.2
ms.date: 08/16/2017
ms.openlocfilehash: a74afd7f073daa46328d60149e2dd90207420a80
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566188"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="79a18-103">Neues in C# 7.2</span><span class="sxs-lookup"><span data-stu-id="79a18-103">What's new in C# 7.2</span></span>

<span data-ttu-id="79a18-104">C# 7.2 ist ein weiteres Release einer Unterversion, das eine Reihe nützlicher Funktionen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="79a18-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="79a18-105">Ein Aspekt für diesen Release ist die effizientere Arbeit mit Werttypen durch Vermeiden unnötiger Kopien oder Zuweisungen.</span><span class="sxs-lookup"><span data-stu-id="79a18-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="79a18-106">Die restlichen Funktionen sind kleine Features, die den Komfort steigern.</span><span class="sxs-lookup"><span data-stu-id="79a18-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="79a18-107">C# 7.2 verwendet das Konfigurationselement [Sprachversionsauswahl](../language-reference/configure-language-version.md), um die Version der Compilersprache auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="79a18-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="79a18-108">Die neuen Sprachfeatures in diesem Release umfassen:</span><span class="sxs-lookup"><span data-stu-id="79a18-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="79a18-109">Verweissemantik mit Werttypen</span><span class="sxs-lookup"><span data-stu-id="79a18-109">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="79a18-110">Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79a18-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="79a18-111">Nicht schließende benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="79a18-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="79a18-112">Positionelle Argumente können auf benannte Argumente folgen.</span><span class="sxs-lookup"><span data-stu-id="79a18-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="79a18-113">Führende Unterstriche in numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="79a18-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="79a18-114">Numerische Literale dürfen jetzt führende Unterstriche vor aufgeführten Stellen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="79a18-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="79a18-115">`private protected`-Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="79a18-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="79a18-116">Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.</span><span class="sxs-lookup"><span data-stu-id="79a18-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="79a18-117">Verweissemantik mit Werttypen</span><span class="sxs-lookup"><span data-stu-id="79a18-117">Reference semantics with value types</span></span>

<span data-ttu-id="79a18-118">In 7.2 eingeführte Sprachfeatures ermöglichen das Arbeiten mit Werttypen bei Verwendung der Verweissemantik.</span><span class="sxs-lookup"><span data-stu-id="79a18-118">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="79a18-119">Sie dienen dazu, die Leistung durch Minimieren des Kopierens von Werttypen zu steigern, ohne die Speicherzuweisungen nach sich zu ziehen, die eine Verwendung von Verweistypen mit sich bringen würde.</span><span class="sxs-lookup"><span data-stu-id="79a18-119">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="79a18-120">Das Feature beinhaltet:</span><span class="sxs-lookup"><span data-stu-id="79a18-120">The features include:</span></span>

 - <span data-ttu-id="79a18-121">Den `in`-Modifizierer für Parameter zur Angabe, dass ein Argument durch Verweis übergeben, von der aufgerufenen Methode aber nicht verändert wird.</span><span class="sxs-lookup"><span data-stu-id="79a18-121">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="79a18-122">Der `ref readonly`-Modifizierer für die Methodenrückgabe, um anzugeben, dass eine Methode ihren Wert als Verweis zurückgibt und keinen Schreibzugriff auf dieses Objekt zulässt.</span><span class="sxs-lookup"><span data-stu-id="79a18-122">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="79a18-123">Die `readonly struct`-Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und ihren Membermethoden als `in`-Parameter übergeben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="79a18-123">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="79a18-124">Die `ref struct`-Deklaration, um anzugeben, dass ein Strukturtyp direkt auf verwalteten Arbeitsspeicher zugreift und immer per Stapel zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="79a18-124">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="79a18-125">Weitere Informationen zu allen diesen Änderungen finden Sie unter [Verwenden von Werttypen mit Verweissemantik](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="79a18-125">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="79a18-126">Nicht schließende benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="79a18-126">Non-trailing named arguments</span></span>

<span data-ttu-id="79a18-127">Methodenaufrufe dürfen jetzt benannte Argumente verwenden, die positionellen Argumenten vorstehen, wenn diese benannten Argumente in der richtigen Position verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79a18-127">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="79a18-128">Weitere Informationen finden Sie unter [Benannte und optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="79a18-128">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="79a18-129">Führende Unterstriche in numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="79a18-129">Leading underscores in numeric literals</span></span>

<span data-ttu-id="79a18-130">Die Implementierung der Unterstützung für Stellentrennzeichen in C# 7.0 ließ den Unterstrich `_` nicht als erstes Zeichen von Literalwerten zu.</span><span class="sxs-lookup"><span data-stu-id="79a18-130">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="79a18-131">Hexadezimale und binäre numerische Literale dürfen jetzt mit einem `_` beginnen.</span><span class="sxs-lookup"><span data-stu-id="79a18-131">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="79a18-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="79a18-132">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="79a18-133">Zugriffsmodifizierer _private protected_</span><span class="sxs-lookup"><span data-stu-id="79a18-133">_private protected_ access modifier</span></span>

<span data-ttu-id="79a18-134">Schließlich zeigt der neue, zusammengesetzte Zugriffsmodifizierer `private protected` an, dass auf ein Element durch eine es enthaltende Klasse oder durch innerhalb der gleichen Assembly deklarierte abgeleitete Klassen zugegriffen werden darf.</span><span class="sxs-lookup"><span data-stu-id="79a18-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="79a18-135">Während `protected internal` den Zugriff durch abgeleitete Klassen oder Klassen, die sich in der gleichen Assembly befinden, erlaubt, schränkt `private protected` den Zugriff auf innerhalb der gleichen Assembly deklarierte abgeleitete Typen ein.</span><span class="sxs-lookup"><span data-stu-id="79a18-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="79a18-136">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="79a18-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
