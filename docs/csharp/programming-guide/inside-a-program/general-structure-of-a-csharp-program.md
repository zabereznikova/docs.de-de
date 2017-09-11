---
title: Allgemeine Struktur eines C#-Programms (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: 21
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
ms.openlocfilehash: d55ac6a6d35e5f47ab26da681afe9fb5555331ec
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="195b8-102">Allgemeine Struktur eines C#-Programms (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="195b8-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="195b8-103">C#-Programme bestehen aus mindestens einer Datei.</span><span class="sxs-lookup"><span data-stu-id="195b8-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="195b8-104">Jede Datei kann 0 (null) oder mehrere Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="195b8-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="195b8-105">Ein Namespace kann Typen, z.B. Klassen, Strukturen, Schnittstellen, Enumerationen und Delegaten sowie andere Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="195b8-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="195b8-106">Im Folgenden wird das Grundgerüst eines C#-Programms dargestellt, das alle diese Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="195b8-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 <span data-ttu-id="195b8-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="195b8-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="195b8-108">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="195b8-108">Related Sections</span></span>  
 <span data-ttu-id="195b8-109">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="195b8-109">For more information:</span></span>  
  
-   [<span data-ttu-id="195b8-110">Klassen</span><span class="sxs-lookup"><span data-stu-id="195b8-110">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="195b8-111">Strukturen</span><span class="sxs-lookup"><span data-stu-id="195b8-111">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="195b8-112">Namespaces</span><span class="sxs-lookup"><span data-stu-id="195b8-112">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="195b8-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="195b8-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="195b8-114">Delegaten</span><span class="sxs-lookup"><span data-stu-id="195b8-114">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="195b8-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="195b8-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="195b8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="195b8-116">See Also</span></span>  
 <span data-ttu-id="195b8-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="195b8-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="195b8-118">[Einblicke in ein C#-Programm](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="195b8-118">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="195b8-119">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="195b8-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="195b8-120">\<paveover>Beispielanwendungen für C#</span><span class="sxs-lookup"><span data-stu-id="195b8-120">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

