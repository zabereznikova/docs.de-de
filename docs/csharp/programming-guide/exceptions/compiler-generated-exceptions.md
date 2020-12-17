---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
description: Erfahren Sie mehr über vom Compiler generierte Ausnahmen. Hier finden Sie eine Liste mit automatisch ausgelösten Ausnahmen und den zugehörigen Fehlerbedingungen.
ms.date: 12/09/2020
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 43bacbb1025bc0af3a5f21979315b3d1b0d61066
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110350"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="3d272-104">Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3d272-104">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="3d272-105">Einige Ausnahmen werden automatisch von der .NET Runtime ausgelöst, wenn grundlegende Operationen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="3d272-105">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="3d272-106">Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3d272-106">These exceptions and their error conditions are listed in the following table.</span></span>

|<span data-ttu-id="3d272-107">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="3d272-107">Exception</span></span>|<span data-ttu-id="3d272-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d272-108">Description</span></span>|
|---------------|-----------------|
|<xref:System.ArithmeticException>|<span data-ttu-id="3d272-109">Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="3d272-109">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="3d272-110">Diese Ausnahme wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Elements mit dem tatsächlichen Typs des Arrays inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="3d272-110">Thrown when an array can't store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|
|<xref:System.DivideByZeroException>|<span data-ttu-id="3d272-111">Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.</span><span class="sxs-lookup"><span data-stu-id="3d272-111">Thrown when an attempt is made to divide an integral value by zero.</span></span>|
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="3d272-112">Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="3d272-112">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|
|<xref:System.InvalidCastException>|<span data-ttu-id="3d272-113">Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="3d272-113">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|
|<xref:System.NullReferenceException>|<span data-ttu-id="3d272-114">Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="3d272-114">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|
|<xref:System.OutOfMemoryException>|<span data-ttu-id="3d272-115">Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="3d272-115">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="3d272-116">Diese Ausnahme weist darauf hin, dass der für die Common Language Runtime verfügbare Arbeitsspeicher aufgebraucht wurde.</span><span class="sxs-lookup"><span data-stu-id="3d272-116">This exception indicates that the memory available to the common language runtime has been exhausted.</span></span>|
|<xref:System.OverflowException>|<span data-ttu-id="3d272-117">Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.</span><span class="sxs-lookup"><span data-stu-id="3d272-117">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|
|<xref:System.StackOverflowException>|<span data-ttu-id="3d272-118">Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.</span><span class="sxs-lookup"><span data-stu-id="3d272-118">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|
|<xref:System.TypeInitializationException>|<span data-ttu-id="3d272-119">Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.</span><span class="sxs-lookup"><span data-stu-id="3d272-119">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3d272-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d272-120">See also</span></span>

- [<span data-ttu-id="3d272-121">try-catch</span><span class="sxs-lookup"><span data-stu-id="3d272-121">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="3d272-122">try-finally</span><span class="sxs-lookup"><span data-stu-id="3d272-122">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="3d272-123">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="3d272-123">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
