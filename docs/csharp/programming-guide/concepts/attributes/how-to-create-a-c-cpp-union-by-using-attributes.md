---
title: 'Vorgehensweise: Erstellen einer Union in C/C++ mit Attributen (C#)'
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: 30a8be9021495aa4cf61010508762999cdf91ff4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315840"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="dbf2b-102">Vorgehensweise: Erstellen einer Union in C/C++ mit Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="dbf2b-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="dbf2b-103">Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="dbf2b-104">Sie können z.B. das erstellen, was als eine Union in C/C++ bekannt ist, indem Sie die mit `StructLayout(LayoutKind.Explicit)`- und `FieldOffset`-Attribute verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf2b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbf2b-105">Example</span></span>  
 <span data-ttu-id="dbf2b-106">In diesem Codesegment beginnen alle Felder von `TestUnion` an derselben Position im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="dbf2b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbf2b-107">Example</span></span>  
 <span data-ttu-id="dbf2b-108">Im Folgenden finden Sie ein weiteres Beispiel, in dem Felder an verschiedenen, explizit festgelegten Orten beginnen.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="dbf2b-109">Die zwei Ganzzahlfelder `i1` und `i2` teilen die gleichen Speicheradressen wie `lg`.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="dbf2b-110">Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn Sie Plattformaufrufe nutzen.</span><span class="sxs-lookup"><span data-stu-id="dbf2b-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf2b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbf2b-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="dbf2b-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dbf2b-112">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dbf2b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dbf2b-113">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="dbf2b-114">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="dbf2b-114">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="dbf2b-115">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="dbf2b-115">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="dbf2b-116">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="dbf2b-116">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="dbf2b-117">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="dbf2b-117">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
