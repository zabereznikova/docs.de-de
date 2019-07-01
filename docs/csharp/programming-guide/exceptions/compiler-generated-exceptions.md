---
title: Vom Compiler generierte Ausnahmen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 28e6ba0c20948aa769a1517c664db80b5beb6b68
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398031"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="dc54a-102">Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="dc54a-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="dc54a-103">Einige Ausnahmen werden automatisch von der Common Language Runtime (CLR) von .NET Framework ausgelöst, wenn grundlegende Operationen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="dc54a-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="dc54a-104">Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="dc54a-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="dc54a-105">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="dc54a-105">Exception</span></span>|<span data-ttu-id="dc54a-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dc54a-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="dc54a-107">Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="dc54a-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="dc54a-108">Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="dc54a-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="dc54a-109">Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.</span><span class="sxs-lookup"><span data-stu-id="dc54a-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="dc54a-110">Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="dc54a-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="dc54a-111">Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="dc54a-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="dc54a-112">Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../../csharp/language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="dc54a-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="dc54a-113">Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../../csharp/language-reference/operators/new-operator.md) zuzuweisen, fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="dc54a-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="dc54a-114">Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="dc54a-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="dc54a-115">Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.</span><span class="sxs-lookup"><span data-stu-id="dc54a-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="dc54a-116">Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.</span><span class="sxs-lookup"><span data-stu-id="dc54a-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="dc54a-117">Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.</span><span class="sxs-lookup"><span data-stu-id="dc54a-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc54a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc54a-118">See also</span></span>

- [<span data-ttu-id="dc54a-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dc54a-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dc54a-120">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="dc54a-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
- [<span data-ttu-id="dc54a-121">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="dc54a-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [<span data-ttu-id="dc54a-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="dc54a-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)
- [<span data-ttu-id="dc54a-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="dc54a-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)
- [<span data-ttu-id="dc54a-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="dc54a-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
