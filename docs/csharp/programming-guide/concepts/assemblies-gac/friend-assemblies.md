---
title: Friend-Assemblys (C#)
ms.date: 07/20/2015
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: e8c295fe23685e39e20a14ff23139339f24564c7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510084"
---
# <a name="friend-assemblies-c"></a><span data-ttu-id="ab8d3-102">Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="ab8d3-102">Friend Assemblies (C#)</span></span>
<span data-ttu-id="ab8d3-103">Eine *Friend-Assembly* ist eine Assembly, die auf die [internen](../../../../csharp/language-reference/keywords/internal.md) Typen und Member einer anderen Assembly zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../../../csharp/language-reference/keywords/internal.md) types and members.</span></span> <span data-ttu-id="ab8d3-104">Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="ab8d3-105">Dies ist insbesondere in folgenden Szenarios nützlich:</span><span class="sxs-lookup"><span data-stu-id="ab8d3-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="ab8d3-106">Wenn der Testcode bei Komponententests in einer separaten Assembly ausgeführt wird, aber Zugriff auf Member in der getesteten Assembly benötigt, die als `internal` markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` .</span></span>  
  
-   <span data-ttu-id="ab8d3-107">Wenn beim Entwickeln einer Klassenbibliothek die Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, aber Zugriff auf Member in vorhandenen Assemblys erfordern, die als `internal` markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` .</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab8d3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab8d3-108">Remarks</span></span>  
 <span data-ttu-id="ab8d3-109">Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="ab8d3-110">Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in Assembly A verwendet, und Assembly `AssemblyB` wird als Friend-Assembly angegeben.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="ab8d3-111">Dadurch erhält Assembly `AssemblyB` Zugriff auf alle Typen und Member in Assembly A, die als `internal` markiert sind.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab8d3-112">Beim Kompilieren einer Assembly (Assembly `AssemblyB`), die auf interne Typen oder interne Member einer anderen Assembly (Assembly *A*) zugreift, müssen Sie den Namen der Ausgabedatei (.exe oder .dll) mit der Compileroption **/out** explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="ab8d3-113">Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="ab8d3-114">Weitere Informationen finden Sie unter [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ab8d3-114">For more information, see [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) .</span></span>  
  
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
  
 <span data-ttu-id="ab8d3-115">Nur Assemblys, die Sie explizit als Friends angeben, können auf `internal`-Typen und -Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-115">Only assemblies that you explicitly specify as friends can access `internal` types and members.</span></span> <span data-ttu-id="ab8d3-116">Wenn zum Beispiel Assembly B ein Friend von Assembly A ist und Assembly C auf Assembly B verweist, hat C keinen Zugriff auf `internal`-Typen in A.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` types in A.</span></span>  
  
 <span data-ttu-id="ab8d3-117">Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="ab8d3-118">Wenn Assembly *A* Assembly *B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ab8d3-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="ab8d3-119">Wenn Assembly *A* einen starken Namen hat, muss Assembly *B* auch einen starken Namen haben.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="ab8d3-120">Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von Assembly *B* verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="ab8d3-121">Der Name der Friend-Assembly, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird, darf nicht der starke Name von Assembly *B* sein: Er darf nicht die Assemblyversion, Kultur, Architektur oder das Token des öffentlichen Schlüssels enthalten.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="ab8d3-122">Wenn Assembly *A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="ab8d3-123">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von nicht signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ab8d3-123">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="ab8d3-124">Wenn Assembly *B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für Assembly *B* über die Projekteinstellung oder bei Verwendung der Befehlszeile die Compileroption `/keyfile` angeben.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="ab8d3-125">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ab8d3-125">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="ab8d3-126">Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:</span><span class="sxs-lookup"><span data-stu-id="ab8d3-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="ab8d3-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="ab8d3-128">Wenn es Hunderte von Typen in Assembly *A* gibt, die Sie für Assembly *B* freigeben möchten, müssen Sie allen <xref:System.Security.Permissions.StrongNameIdentityPermission> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="ab8d3-129">Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="ab8d3-130">Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="ab8d3-131">Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als `internal` deklariert.</span><span class="sxs-lookup"><span data-stu-id="ab8d3-131">If you use a friend assembly, the shared types are declared as `internal`.</span></span>  
  
 <span data-ttu-id="ab8d3-132">Informationen darüber, wie Sie auf `internal`-Typen und -Methoden einer Assembly aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule) zugreifen können, finden Sie unter [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ab8d3-132">For information about how to access an assembly's `internal` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8d3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab8d3-133">See Also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
- <xref:System.Security.Permissions.StrongNameIdentityPermission>  
- [<span data-ttu-id="ab8d3-134">How to: Create Unsigned Friend Assemblies (C#) (Vorgehensweise: Erstellen von nicht signierten Friend-Assemblys (C#))</span><span class="sxs-lookup"><span data-stu-id="ab8d3-134">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
- [<span data-ttu-id="ab8d3-135">Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="ab8d3-135">How to: Create Signed Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
- [<span data-ttu-id="ab8d3-136">Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))</span><span class="sxs-lookup"><span data-stu-id="ab8d3-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="ab8d3-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ab8d3-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
