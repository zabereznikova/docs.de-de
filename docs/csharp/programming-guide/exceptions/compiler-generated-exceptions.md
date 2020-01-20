---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 2a6b2c3fa053f1c555856df8098975340e78e2b2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705313"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="c09a8-102">Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c09a8-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="c09a8-103">Einige Ausnahmen werden automatisch von der Common Language Runtime (CLR) von .NET Framework ausgelöst, wenn grundlegende Operationen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="c09a8-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="c09a8-104">Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c09a8-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="c09a8-105">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="c09a8-105">Exception</span></span>|<span data-ttu-id="c09a8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c09a8-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="c09a8-107">Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c09a8-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="c09a8-108">Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="c09a8-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="c09a8-109">Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.</span><span class="sxs-lookup"><span data-stu-id="c09a8-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="c09a8-110">Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="c09a8-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="c09a8-111">Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c09a8-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="c09a8-112">Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="c09a8-112">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="c09a8-113">Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c09a8-113">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="c09a8-114">Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="c09a8-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="c09a8-115">Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.</span><span class="sxs-lookup"><span data-stu-id="c09a8-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="c09a8-116">Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.</span><span class="sxs-lookup"><span data-stu-id="c09a8-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="c09a8-117">Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.</span><span class="sxs-lookup"><span data-stu-id="c09a8-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c09a8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c09a8-118">See also</span></span>

- [<span data-ttu-id="c09a8-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c09a8-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c09a8-120">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="c09a8-120">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="c09a8-121">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="c09a8-121">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="c09a8-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="c09a8-122">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="c09a8-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="c09a8-123">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="c09a8-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="c09a8-124">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
