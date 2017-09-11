---
title: 'Vorgehensweise: Erstellen einer Union in C/C++ mit Attributen (C#)'
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
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
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
ms.openlocfilehash: 4532829080d994cf4cec92d64a12e3bf1890dc6a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="a1ac0-102">Vorgehensweise: Erstellen einer Union in C/C++ mit Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="a1ac0-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="a1ac0-103">Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="a1ac0-104">Sie können z.B. das erstellen, was als eine Union in C/C++ bekannt ist, indem Sie die mit `StructLayout(LayoutKind.Explicit)`- und `FieldOffset`-Attribute verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ac0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1ac0-105">Example</span></span>  
 <span data-ttu-id="a1ac0-106">In diesem Codesegment beginnen alle Felder von `TestUnion` an derselben Position im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="a1ac0-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1ac0-107">Example</span></span>  
 <span data-ttu-id="a1ac0-108">Im Folgenden finden Sie ein weiteres Beispiel, in dem Felder an verschiedenen, explizit festgelegten Orten beginnen.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="a1ac0-109">Die zwei Ganzzahlfelder `i1` und `i2` teilen die gleichen Speicheradressen wie `lg`.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="a1ac0-110">Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn Sie Plattformaufrufe nutzen.</span><span class="sxs-lookup"><span data-stu-id="a1ac0-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ac0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1ac0-111">See Also</span></span>  
 <span data-ttu-id="a1ac0-112"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="a1ac0-112"><xref:System.Reflection></span></span>   
 <span data-ttu-id="a1ac0-113"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="a1ac0-113"><xref:System.Attribute></span></span>   
 <span data-ttu-id="a1ac0-114">[C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1ac0-114">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a1ac0-115">[Attribute](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="a1ac0-115">[Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
 <span data-ttu-id="a1ac0-116">[Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="a1ac0-116">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="a1ac0-117">[Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1ac0-117">[Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 <span data-ttu-id="a1ac0-118">[Erstellen benutzerdefinierter Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="a1ac0-118">[Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
 [<span data-ttu-id="a1ac0-119">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="a1ac0-119">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

