---
title: Kovarianz und Kontravarianz (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e1282f84171fa75db9656634a83f7cd5d4b9ac82
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="99607-102">Kovarianz und Kontravarianz (C#)</span><span class="sxs-lookup"><span data-stu-id="99607-102">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="99607-103">Kovarianz und Kontravarianz in C# ermöglichen die implizite Referenzkonvertierung für Arraytypen, Delegattypen und generische Typargumente.</span><span class="sxs-lookup"><span data-stu-id="99607-103">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="99607-104">Die Kovarianz behält die Zuweisungskompatibilität bei und die Kontravarianz kehrt sie um.</span><span class="sxs-lookup"><span data-stu-id="99607-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="99607-105">Der folgende Code veranschaulicht den Unterschied zwischen Zuweisungskompatibilität, Kovarianz und Kontravarianz.</span><span class="sxs-lookup"><span data-stu-id="99607-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.   
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.   
object obj = str;  
  
// Covariance.   
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument   
// is assigned to an object instantiated with a less derived type argument.   
// Assignment compatibility is preserved.   
IEnumerable<object> objects = strings;  
  
// Contravariance.             
// Assume that the following method is in the class:   
// static void SetObject(object o) { }   
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument   
// is assigned to an object instantiated with a more derived type argument.   
// Assignment compatibility is reversed.   
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="99607-106">Die Kovarianz für Arrays ermöglicht die implizite Konvertierung eines Arrays mit einem stärker abgeleiteten Typ zu einem Array mit einem schwächer abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="99607-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="99607-107">Dieser Vorgang ist jedoch nicht typsicher, wie im folgenden Codebeispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="99607-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="99607-108">Die Unterstützung von Kovarianz und Kontravarianz für Methodengruppen ermöglicht es, Methodensignaturen mit Delegattypen abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="99607-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="99607-109">Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz).</span><span class="sxs-lookup"><span data-stu-id="99607-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="99607-110">Weitere Informationen finden Sie unter [Variance in Delegates (C#) (Varianz in Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Using Variance in Delegates (C#) (Verwenden von Varianz in Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="99607-110">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="99607-111">Im folgenden Codebeispiel wird die Unterstützung von Methodengruppen durch Kovarianz und Kontravarianz veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="99607-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="99607-112">In .NET Framework 4 oder höher unterstützt C# die Kovarianz und Kontravarianz in generischen Schnittstellen und Delegaten und ermöglicht die implizite Konvertierung von generischen Typparametern.</span><span class="sxs-lookup"><span data-stu-id="99607-112">In .NET Framework 4 or newer C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="99607-113">Weitere Informationen finden Sie unter [Variance in Generic Interfaces (C#) (Varianz in generischen Schnittstellen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) und [Variance in Delegates (C#) (Varianz in Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="99607-113">For more information, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="99607-114">Das folgende Codebeispiel zeigt die implizite Verweiskonvertierung bei generischen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="99607-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="99607-115">Generische Schnittstellen oder Delegate werden als *variant* bezeichnet, wenn deren generische Parameter als kovariant oder kontravariant deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="99607-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="99607-116">C# ermöglicht es Ihnen, eigene variante Schnittstellen oder Delegate zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99607-116">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="99607-117">Weitere Informationen finden Sie unter [Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) und [Variance in Delegates (C#) (Varianz in Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="99607-117">For more information, see [Creating Variant Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="99607-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="99607-118">Related Topics</span></span>  
  
|<span data-ttu-id="99607-119">Titel</span><span class="sxs-lookup"><span data-stu-id="99607-119">Title</span></span>|<span data-ttu-id="99607-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99607-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="99607-121">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99607-121">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="99607-122">Erläutert Ko- und Kontravarianz in generischen Schnittstellen und enthält eine Liste der Varianten generischen Schnittstellen in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99607-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="99607-123">Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))</span><span class="sxs-lookup"><span data-stu-id="99607-123">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="99607-124">Zeigt, wie benutzerdefinierte variante Schnittstellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="99607-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="99607-125">Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))</span><span class="sxs-lookup"><span data-stu-id="99607-125">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="99607-126">Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei <xref:System.Collections.Generic.IEnumerable%601>- und <xref:System.IComparable%601>-Schnittstellen bei der Wiederverwendung Ihres Codes helfen kann.</span><span class="sxs-lookup"><span data-stu-id="99607-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="99607-127">Variance in Delegates (C#) (Varianz bei Delegaten (C#))</span><span class="sxs-lookup"><span data-stu-id="99607-127">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="99607-128">Erläutert Ko- und Kontravarianz in generischen und nicht generischen Delegaten und stellt eine Liste von varianten generischen Delegaten im .NET Framework bereit.</span><span class="sxs-lookup"><span data-stu-id="99607-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="99607-129">Using Variance in Delegates (C#) (Verwenden von Varianz in Delegaten (C#))</span><span class="sxs-lookup"><span data-stu-id="99607-129">Using Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="99607-130">Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz in nicht generischen Delegaten verwendet werden kann, um Methodensignaturen mit Delegattypen abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="99607-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="99607-131">Verwenden von Varianz für die generischen Delegaten Func und Action (C#)</span><span class="sxs-lookup"><span data-stu-id="99607-131">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="99607-132">Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei `Func`- und `Action`-Delegaten bei der Wiederverwendung Ihres Codes helfen kann.</span><span class="sxs-lookup"><span data-stu-id="99607-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|

