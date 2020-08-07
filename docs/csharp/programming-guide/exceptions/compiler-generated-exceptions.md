---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
description: Erfahren Sie mehr über vom Compiler generierte Ausnahmen. Hier finden Sie eine Liste mit automatisch ausgelösten Ausnahmen und den zugehörigen Fehlerbedingungen.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1def83f72e83976ac672ec35169b4950a20ef54e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302060"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="acc0e-104">Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="acc0e-104">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="acc0e-105">Einige Ausnahmen werden automatisch von der .NET Runtime ausgelöst, wenn grundlegende Operationen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="acc0e-105">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="acc0e-106">Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="acc0e-106">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="acc0e-107">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="acc0e-107">Exception</span></span>|<span data-ttu-id="acc0e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acc0e-108">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="acc0e-109">Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="acc0e-109">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="acc0e-110">Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="acc0e-110">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="acc0e-111">Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.</span><span class="sxs-lookup"><span data-stu-id="acc0e-111">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="acc0e-112">Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="acc0e-112">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="acc0e-113">Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="acc0e-113">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="acc0e-114">Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="acc0e-114">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="acc0e-115">Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="acc0e-115">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="acc0e-116">Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="acc0e-116">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="acc0e-117">Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.</span><span class="sxs-lookup"><span data-stu-id="acc0e-117">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="acc0e-118">Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.</span><span class="sxs-lookup"><span data-stu-id="acc0e-118">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="acc0e-119">Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.</span><span class="sxs-lookup"><span data-stu-id="acc0e-119">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acc0e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acc0e-120">See also</span></span>

- [<span data-ttu-id="acc0e-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="acc0e-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="acc0e-122">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="acc0e-122">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="acc0e-123">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="acc0e-123">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="acc0e-124">try-catch</span><span class="sxs-lookup"><span data-stu-id="acc0e-124">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="acc0e-125">try-finally</span><span class="sxs-lookup"><span data-stu-id="acc0e-125">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="acc0e-126">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="acc0e-126">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
