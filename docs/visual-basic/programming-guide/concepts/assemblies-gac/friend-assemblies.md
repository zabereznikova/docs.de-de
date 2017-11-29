---
title: Friend-Assemblys (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d3a37629582e4fc2606afaf606735464c0d247a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="db352-102">Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db352-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="db352-103">Ein *Friend-Assembly* ist eine Assembly, die auf einer anderen Assembly zugreifen kann ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="db352-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="db352-104">Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="db352-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="db352-105">Dies ist insbesondere in folgenden Szenarios nützlich:</span><span class="sxs-lookup"><span data-stu-id="db352-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="db352-106">Bei Komponententests, wenn Testcode ausgeführt, in wird eine separate Assembly jedoch erfordert Zugriff auf Member der zu testenden Assembly, die als markiert sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="db352-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="db352-107">Wenn Sie eine Klassenbibliothek entwickeln und Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, jedoch benötigen Sie Zugriff auf Elemente in vorhandene Assemblys, die als gekennzeichnet sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="db352-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db352-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db352-108">Remarks</span></span>  
 <span data-ttu-id="db352-109">Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="db352-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="db352-110">Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in Assembly A verwendet, und Assembly `AssemblyB` wird als Friend-Assembly angegeben.</span><span class="sxs-lookup"><span data-stu-id="db352-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="db352-111">Dadurch erhält Assembly `AssemblyB` Zugriff auf alle Typen und Member in Assembly A, die als `Friend` markiert sind.</span><span class="sxs-lookup"><span data-stu-id="db352-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db352-112">Beim Kompilieren einer Assembly (Assembly `AssemblyB`), die auf interne Typen oder interne Member einer anderen Assembly (Assembly *A*) zugreift, müssen Sie den Namen der Ausgabedatei (.exe oder .dll) mit der Compileroption **/out** explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="db352-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="db352-113">Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="db352-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="db352-114">Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="db352-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
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
  
 <span data-ttu-id="db352-115">Nur Assemblys, die Sie explizit als Friends angeben, können auf `Friend`-Typen und -Member zugreifen.</span><span class="sxs-lookup"><span data-stu-id="db352-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="db352-116">Wenn zum Beispiel Assembly B ein Friend von Assembly A ist und Assembly C auf Assembly B verweist, hat C keinen Zugriff auf `Friend`-Typen in A.</span><span class="sxs-lookup"><span data-stu-id="db352-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="db352-117">Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="db352-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="db352-118">Wenn Assembly *A* Assembly *B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:</span><span class="sxs-lookup"><span data-stu-id="db352-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="db352-119">Wenn Assembly *A* einen starken Namen hat, muss Assembly *B* auch einen starken Namen haben.</span><span class="sxs-lookup"><span data-stu-id="db352-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="db352-120">Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von Assembly *B* verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db352-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="db352-121">Der Name der Friend-Assembly, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird, darf nicht der starke Name von Assembly *B* sein: Er darf nicht die Assemblyversion, Kultur, Architektur oder das Token des öffentlichen Schlüssels enthalten.</span><span class="sxs-lookup"><span data-stu-id="db352-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="db352-122">Wenn Assembly *A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="db352-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="db352-123">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie nicht signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="db352-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="db352-124">Wenn Assembly *B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für Assembly *B* über die Projekteinstellung oder bei Verwendung der Befehlszeile die Compileroption `/keyfile` angeben.</span><span class="sxs-lookup"><span data-stu-id="db352-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="db352-125">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="db352-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="db352-126">Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:</span><span class="sxs-lookup"><span data-stu-id="db352-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="db352-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.</span><span class="sxs-lookup"><span data-stu-id="db352-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="db352-128">Wenn es Hunderte von Typen in Assembly *A* gibt, die Sie für Assembly *B* freigeben möchten, müssen Sie allen <xref:System.Security.Permissions.StrongNameIdentityPermission> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="db352-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="db352-129">Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.</span><span class="sxs-lookup"><span data-stu-id="db352-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="db352-130">Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="db352-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="db352-131">Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als `Friend` deklariert.</span><span class="sxs-lookup"><span data-stu-id="db352-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="db352-132">Informationen zum Zugreifen auf einer Assembly `Friend` Typen und Methoden aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule) finden Sie unter [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="db352-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db352-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db352-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [<span data-ttu-id="db352-134">Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db352-134">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="db352-135">Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db352-135">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="db352-136">Assemblys und der globale Assemblycache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db352-136">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="db352-137">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="db352-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
