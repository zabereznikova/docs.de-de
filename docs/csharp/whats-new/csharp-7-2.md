---
title: Was ist neu in c# 7.2
description: "Eine Übersicht über neue Funktionen in c# 7.2."
keywords: C#-Sprachentwurf 7.2, Visual Studio-2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="3985f-104">Was ist neu in c# 7.2</span><span class="sxs-lookup"><span data-stu-id="3985f-104">What's new in C# 7.2</span></span>

<span data-ttu-id="3985f-105">C#-7.2 ist einem anderen Punkt-Version, die eine Reihe nützlicher Features hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3985f-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="3985f-106">Ein Design für diese Version ist effizienter Werttypen arbeitet, indem Sie unnötige Kopien oder Zuordnungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3985f-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="3985f-107">Die übrigen Funktionen sind kleine, nice ist-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3985f-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="3985f-108">C#-7.2 verwendet die [Version Sprachauswahl](csharp-7-1.md#language-version-selection) Konfigurationselement, wählen Sie die Sprachversion der Compiler.</span><span class="sxs-lookup"><span data-stu-id="3985f-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="3985f-109">Die neuen Sprachfeatures in dieser Version sind:</span><span class="sxs-lookup"><span data-stu-id="3985f-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="3985f-110">Verweissemantik mit Werttypen</span><span class="sxs-lookup"><span data-stu-id="3985f-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="3985f-111">Eine Kombination von Syntax Verbesserungen, die Arbeit mit Werttypen mit Verweissemantik zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3985f-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="3985f-112">Nachfolgende auf nicht benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="3985f-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="3985f-113">Benannte Argumente können Positionsargumente folgen.</span><span class="sxs-lookup"><span data-stu-id="3985f-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="3985f-114">Führende Unterstriche in numerische Literale</span><span class="sxs-lookup"><span data-stu-id="3985f-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="3985f-115">Numerische Literale können jetzt führende Unterstriche, bevor Sie alle gedruckten Ziffern haben.</span><span class="sxs-lookup"><span data-stu-id="3985f-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="3985f-116">`private protected`Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="3985f-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="3985f-117">Die `private protected` Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen in derselben Assembly.</span><span class="sxs-lookup"><span data-stu-id="3985f-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="3985f-118">Verweissemantik mit Werttypen</span><span class="sxs-lookup"><span data-stu-id="3985f-118">Reference semantics with value types</span></span>

<span data-ttu-id="3985f-119">7.2 eingeführte Sprachfunktionen können Sie die mit Verweissemantik mit Werttypen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3985f-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="3985f-120">Sie dienen zum Erhöhen der Leistung durch Minimierung von Werttypen ohne die speicherbelegungen zugeordneten mit Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="3985f-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="3985f-121">Die Features umfassen:</span><span class="sxs-lookup"><span data-stu-id="3985f-121">The features include:</span></span>

 - <span data-ttu-id="3985f-122">Die `in` Modifizierer auf Parametern, um anzugeben, dass ein Argument als Verweis wird übergeben jedoch nicht von der aufgerufenen Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="3985f-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="3985f-123">Die `ref readonly` Methode zurückgegeben wird, um anzugeben, dass eine Methode als Verweis den Wert zurückgibt, sondern schreibt, der diesem Objekt kann keine-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="3985f-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="3985f-124">Die `readonly struct` Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und sollte, als übergeben werden ein `in` Parameter an die Membermethoden.</span><span class="sxs-lookup"><span data-stu-id="3985f-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="3985f-125">Die `ref struct` Deklaration, um anzugeben, dass ein Strukturtyp greift direkt auf verwalteten Speicher und immer Stapel zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="3985f-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="3985f-126">Erfahren Sie mehr über diese Änderungen in [Verweissemantik Werttypen mit](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="3985f-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="3985f-127">Nachfolgende auf nicht benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="3985f-127">Non-trailing named arguments</span></span>

<span data-ttu-id="3985f-128">Methodenaufrufe können jetzt benannte Argumente, die Positionsargumente vorausgehen, wenn dieser benannten Argumenten in den korrekten Positionen befinden.</span><span class="sxs-lookup"><span data-stu-id="3985f-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="3985f-129">Weitere Informationen finden Sie unter [benannte und optionale Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="3985f-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="3985f-130">Führende Unterstriche in numerische Literale</span><span class="sxs-lookup"><span data-stu-id="3985f-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="3985f-131">Die Implementierung der Unterstützung für Trennzeichen für Ziffern in c# 7.0 nicht zulassen der `_` auf das erste Zeichen Literalwert sein.</span><span class="sxs-lookup"><span data-stu-id="3985f-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="3985f-132">Hex und binäre numerische Literale beginnt nun mit einem `_`.</span><span class="sxs-lookup"><span data-stu-id="3985f-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="3985f-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3985f-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="3985f-134">Schließlich, einen neuen zusammengesetzten Zugriffsmodifizierer: `private protected` gibt an, dass ein Member von abgeleiteten Klassen zugegriffen werden kann, die in der gleichen Assembly deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="3985f-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="3985f-135">Während `protected internal` ermöglicht den Zugriff von abgeleiteten Klassen oder Klassen, die in der gleichen Assembly `private protected` schränkt den Zugriff auf abgeleitete Typen, die in der gleichen Assembly deklariert.</span><span class="sxs-lookup"><span data-stu-id="3985f-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="3985f-136">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="3985f-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
