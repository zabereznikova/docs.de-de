---
title: Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d8fbae9272b34dd4d010199470c930c846cd1b74
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="d1fac-102">Vom Compiler generierte Ausnahmen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d1fac-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="d1fac-103">Einige Ausnahmen werden automatisch von der Common Language Runtime (CLR) von .NET Framework ausgelöst, wenn grundlegende Operationen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="d1fac-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="d1fac-104">Diese Ausnahmen und die entsprechenden Fehlerbedingungen sind in der folgenden Tabellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d1fac-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="d1fac-105">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d1fac-105">Exception</span></span>|<span data-ttu-id="d1fac-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1fac-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="d1fac-107">Eine Basisklasse für Ausnahmen (z.B. <xref:System.DivideByZeroException> und <xref:System.OverflowException>), die während arithmetischer Operationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="d1fac-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="d1fac-108">Wird ausgelöst, wenn ein Array ein gegebenes Element nicht speichern kann, weil der tatsächliche Typ des Element mit dem tatsächlichen Typs des Arrays inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="d1fac-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="d1fac-109">Wird ausgelöst, wenn versucht wird, einen Integralwert durch null zu teilen.</span><span class="sxs-lookup"><span data-stu-id="d1fac-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="d1fac-110">Wird ausgelöst, wenn versucht wird, ein Array zu indizieren, während der Index weniger als null ist oder sich außerhalb der Arraygrenzen befindet.</span><span class="sxs-lookup"><span data-stu-id="d1fac-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="d1fac-111">Wird ausgelöst, wenn eine explizite Konvertierung eines Basistyps in eine Schnittstelle oder in einen abgeleiteten Typen zur Laufzeit fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="d1fac-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="d1fac-112">Wird ausgelöst, wenn versucht wird, auf ein Objekt zu verweisen, dessen Wert [NULL](../../../csharp/language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="d1fac-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="d1fac-113">Wird ausgelöst, wenn der Versuch, Speicher mithilfe des Operators [new](../../../csharp/language-reference/keywords/new-operator.md) zuzuweisen, fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="d1fac-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/keywords/new-operator.md) operator fails.</span></span> <span data-ttu-id="d1fac-114">Dies weist darauf hin, dass der für die Common Language Runtime verfügbare Speicher ausgeschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="d1fac-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="d1fac-115">Wird ausgelöst, wenn eine arithmetische Operation im Kontext `checked` überläuft.</span><span class="sxs-lookup"><span data-stu-id="d1fac-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="d1fac-116">Wird ausgelöst, wenn der Ausführungsstapel durch zu viele ausstehende Methodenaufrufe ausgeschöpft ist; weist für gewöhnlich auf eine tiefe oder unendliche Rekursion hin.</span><span class="sxs-lookup"><span data-stu-id="d1fac-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="d1fac-117">Wird ausgelöst, wenn ein statischer Konstruktor eine Ausnahme auslöst, und keine kompatiblen `catch`-Klausel vorhanden ist, die sie abfangen könnte.</span><span class="sxs-lookup"><span data-stu-id="d1fac-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1fac-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1fac-118">See Also</span></span>  
 <span data-ttu-id="d1fac-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d1fac-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d1fac-120">[Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="d1fac-120">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="d1fac-121">[Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md) </span><span class="sxs-lookup"><span data-stu-id="d1fac-121">[Exception Handling](../../../csharp/programming-guide/exceptions/exception-handling.md) </span></span>  
 <span data-ttu-id="d1fac-122">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="d1fac-122">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="d1fac-123">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="d1fac-123">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="d1fac-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="d1fac-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)

