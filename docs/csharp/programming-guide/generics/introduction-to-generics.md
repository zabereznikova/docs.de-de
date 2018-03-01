---
title: "Einführung in Generika (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61baf26c9f942a59e3787ca55a2ac6a824410608
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2018
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="923bf-102">Einführung in Generika (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="923bf-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="923bf-103">Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz so, wie es ihre nicht generischen Gegenstücke nicht können.</span><span class="sxs-lookup"><span data-stu-id="923bf-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="923bf-104">Generika werden am häufigsten für Auflistungen und deren Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="923bf-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="923bf-105">Version 2.0 der .NET Framework-Klassenbibliothek bietet einen neuen Namespace, <xref:System.Collections.Generic>, der mehrere neue generikabasierte Auflistungsklassen enthält.</span><span class="sxs-lookup"><span data-stu-id="923bf-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="923bf-106">Es wird empfohlen, dass alle Anwendungen für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 und höher die neue generische Auflistungsklasse statt der älteren nicht generischen Gegenstücke wie etwa <xref:System.Collections.ArrayList> verwenden.</span><span class="sxs-lookup"><span data-stu-id="923bf-106">It is recommended that all applications that target the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="923bf-107">Weitere Informationen finden Sie unter [Generika in der .NET Framework-Klassenbibliothek](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="923bf-107">For more information, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="923bf-108">Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="923bf-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="923bf-109">Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="923bf-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="923bf-110">(In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden., die von der .NET Framework-Klassenbibliothek bereitgestellt wird, statt Ihre eigene zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="923bf-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="923bf-111">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="923bf-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="923bf-112">Als Typ eines Methodenparameters in der Methode `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="923bf-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="923bf-113">Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.</span><span class="sxs-lookup"><span data-stu-id="923bf-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="923bf-114">Als Typ des privaten Members `data` in der geschachtelten Klasse.</span><span class="sxs-lookup"><span data-stu-id="923bf-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="923bf-115">Beachten Sie, dass T für die geschachtelte Klasse `Node` zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="923bf-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="923bf-116">Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="923bf-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 <span data-ttu-id="923bf-117">Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="923bf-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="923bf-118">Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="923bf-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="923bf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="923bf-119">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="923bf-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="923bf-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="923bf-121">Generika</span><span class="sxs-lookup"><span data-stu-id="923bf-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
