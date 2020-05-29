---
title: Friend-Assemblys
description: Eine Friend-Assembly ist eine .NET-Assembly, die auf die Friend-Typen (Visual Basic) oder internen Typen (C#) und Member einer anderen Assembly zugreifen kann.
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: 105621da2bd418c6294fa2bbec474809599cb6a5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378932"
---
# <a name="friend-assemblies"></a><span data-ttu-id="ba91c-103">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ba91c-103">Friend assemblies</span></span>

<span data-ttu-id="ba91c-104">Eine *Friend-Assembly* ist eine Assembly, die auf die [Friend-](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) oder [internen](../../csharp/language-reference/keywords/internal.md) (C#) Typen und Member einer anderen Assembly zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ba91c-104">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members.</span></span> <span data-ttu-id="ba91c-105">Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ba91c-105">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="ba91c-106">Dies ist insbesondere in folgenden Szenarios nützlich:</span><span class="sxs-lookup"><span data-stu-id="ba91c-106">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="ba91c-107">Wenn der Testcode bei Komponententests in einer separaten Assembly ausgeführt wird, aber Zugriff auf Member in der getesteten Assembly benötigt, die als `internal` in C# oder `Friend` in Visual Basic markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba91c-107">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="ba91c-108">Wenn beim Entwickeln einer Klassenbibliothek die Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, aber Zugriff auf Member in vorhandenen Assemblys erfordern, die als `internal` in C# oder `Friend` in Visual Basic markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba91c-108">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba91c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba91c-109">Remarks</span></span>

<span data-ttu-id="ba91c-110">Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ba91c-110">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="ba91c-111">Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in *Assembly A* verwendet, und *Assembly B* wird als Friend-Assembly angegeben.</span><span class="sxs-lookup"><span data-stu-id="ba91c-111">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly.</span></span> <span data-ttu-id="ba91c-112">Dadurch erhält *Assembly B* Zugriff auf alle Typen und Member in *Assembly A*, die als `internal` (C#) oder `Friend` (Visual Basic) markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba91c-112">This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="ba91c-113">Wenn Sie eine Assembly wie *Assembly B* kompilieren, die auf interne Typen oder Member einer anderen Assembly wie *Assembly A* zugreift, müssen Sie den Namen der Ausgabedatei ( *.exe* oder *.dll*) explizit mithilfe der Compileroption **-out** festlegen.</span><span class="sxs-lookup"><span data-stu-id="ba91c-113">When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file (*.exe* or *.dll*) by using the **-out** compiler option.</span></span> <span data-ttu-id="ba91c-114">Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ba91c-114">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="ba91c-115">Weitere Informationen hierzu finden Sie unter [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="ba91c-115">For more information, see [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

```vb
Imports System.Runtime.CompilerServices
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

<span data-ttu-id="ba91c-116">Nur Assemblys, die Sie explizit als Friends angeben, können auf die Typen und Member `internal` (C#) oder `Friend` (Visual Basic) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ba91c-116">Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span> <span data-ttu-id="ba91c-117">Wenn *Assembly B* beispielsweise ein Friend von *Assembly A* ist und *Assembly C* auf *Assembly B* verweist, verfügt *Assembly C* nicht über Zugriff auf die Typen `internal` (C#) oder `Friend` (Visual Basic) in *Assembly A*.</span><span class="sxs-lookup"><span data-stu-id="ba91c-117">For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.</span></span>

<span data-ttu-id="ba91c-118">Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ba91c-118">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="ba91c-119">Wenn *Assembly A* die *Assembly B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ba91c-119">If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="ba91c-120">Wenn *Assembly A* einen starken Namen hat, muss *Assembly B* auch einen starken Namen haben.</span><span class="sxs-lookup"><span data-stu-id="ba91c-120">If *Assembly A* is strong named, *AssemblyB* must also be strong named.</span></span> <span data-ttu-id="ba91c-121">Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von *Assembly B* verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba91c-121">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.</span></span>

     <span data-ttu-id="ba91c-122">Der Name der Friend-Assembly, der an das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribut übergeben wird, kann nicht der starke Name der *Assembly B* sein.</span><span class="sxs-lookup"><span data-stu-id="ba91c-122">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*.</span></span> <span data-ttu-id="ba91c-123">Fügen Sie keine Assemblyversion, Kultur, Architektur und kein öffentliches Schlüsseltoken ein.</span><span class="sxs-lookup"><span data-stu-id="ba91c-123">Don't include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="ba91c-124">Wenn *Assembly A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="ba91c-124">If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="ba91c-125">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys](create-unsigned-friend.md).</span><span class="sxs-lookup"><span data-stu-id="ba91c-125">For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).</span></span>

- <span data-ttu-id="ba91c-126">Wenn *Assembly B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für *Assembly B* über die Projekteinstellung oder über die Compileroption `/keyfile` in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="ba91c-126">If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="ba91c-127">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von signierten Friend-Assemblys](create-signed-friend.md).</span><span class="sxs-lookup"><span data-stu-id="ba91c-127">For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).</span></span>

 <span data-ttu-id="ba91c-128">Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:</span><span class="sxs-lookup"><span data-stu-id="ba91c-128">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="ba91c-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="ba91c-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="ba91c-130">Wenn Hunderte Typen in *Assembly A* vorliegen, die Sie für *Assembly B* freigeben möchten, müssen Sie <xref:System.Security.Permissions.StrongNameIdentityPermission> zu allen Typen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba91c-130">If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="ba91c-131">Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ba91c-131">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="ba91c-132">Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ba91c-132">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="ba91c-133">Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen in `internal` (C#) oder `Friend` (Visual Basic) deklariert.</span><span class="sxs-lookup"><span data-stu-id="ba91c-133">If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).</span></span>

<span data-ttu-id="ba91c-134">Informationen darüber, wie Sie über eine Moduldatei (eine Datei mit der Dateierweiterung *.netmodule*) auf die Typen und Methoden `internal` (C#) oder `Friend` (Visual Basic) zugreifen, finden Sie unter [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) oder [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="ba91c-134">For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba91c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba91c-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="ba91c-136">How to: Erstellen von unsignierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ba91c-136">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="ba91c-137">How to: Erstellen von signierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ba91c-137">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="ba91c-138">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="ba91c-138">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="ba91c-139">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ba91c-139">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ba91c-140">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba91c-140">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
