---
title: Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23c9167bf6a632b53202bdc56aebb2248065e967
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="987f8-102">Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="987f8-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="987f8-103">Ein *Friend-Assembly* ist eine Assembly, die auf einer anderen Assembly zugreifen kann [Freund](../../../../visual-basic/language-reference/modifiers/friend.md) Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="987f8-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="987f8-104">Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie nicht mehr Typen und Member als öffentlich für sie von anderen Assemblys erfolgen markieren.</span><span class="sxs-lookup"><span data-stu-id="987f8-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="987f8-105">Dies ist besonders hilfreich, in den folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="987f8-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="987f8-106">Bei Komponententests, wenn Testcode ausgeführt, in wird eine separate Assembly muss jedoch Zugriff auf Member der zu testenden Assembly, die als markiert sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="987f8-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="987f8-107">Wenn Sie entwickeln eine Klassenbibliothek und Ergänzungen der Bibliothek in separate Assemblys enthalten sind, aber erfordern Zugriff auf Elemente in vorhandenen Assemblys, die als markiert sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="987f8-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="987f8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="987f8-108">Remarks</span></span>  
 <span data-ttu-id="987f8-109">Sie können die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut, um eine oder mehrere Friend-Assemblys für eine bestimmte Assembly identifizieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="987f8-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="987f8-110">Im folgenden Beispiel wird das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribut in Assembly A und Assembly gibt `AssemblyB` als Friend-Assembly.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="987f8-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="987f8-111">Dadurch erhält die Assembly `AssemblyB` Zugriff auf alle Typen und Member in der Assembly, die als gekennzeichnete `Friend`.</span><span class="sxs-lookup"><span data-stu-id="987f8-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="987f8-112">Beim Kompilieren einer Assemblys (Assembly `AssemblyB`), die wird der Zugriff auf interne Typen oder internen Member einer anderen Assembly (Assembly *ein*), müssen Sie den Namen der Ausgabedatei (.exe oder .dll) explizit angeben, mit der **/out** (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="987f8-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="987f8-113">Dies ist erforderlich, da der Compiler noch nicht den Namen für die Assembly generiert wurde, zu dem Zeitpunkt erstellt wird, die es externen Verweise gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="987f8-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="987f8-114">Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="987f8-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
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
  
 <span data-ttu-id="987f8-115">Nur Assemblys, die Sie explizit angeben, wie Freunde zugreifen können `Friend` Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="987f8-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="987f8-116">Beispielsweise wird Assembly B ein Freund von Assembly A und Assembly C auf Assembly B, C hat keinen Zugriff auf `Friend` Typen in A.</span><span class="sxs-lookup"><span data-stu-id="987f8-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="987f8-117">Der Compiler führt eine grundlegende Überprüfung der Namen der Friend-Assembly übergeben, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="987f8-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="987f8-118">Wenn Assembly *ein* deklariert *B* als Friend-Assembly, die Validierungsregeln werden wie folgt:</span><span class="sxs-lookup"><span data-stu-id="987f8-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="987f8-119">Wenn Assembly *ein* ist stark benannte Assembly *B* muss auch starken Namen.</span><span class="sxs-lookup"><span data-stu-id="987f8-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="987f8-120">Der Name der Friend-Assembly, die an das Attribut übergeben wird enthalten den Namen der Assembly und der öffentliche Schlüssel des Schlüssel mit starkem Namen, die zum Signieren der Assembly verwendet wird *B*.</span><span class="sxs-lookup"><span data-stu-id="987f8-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="987f8-121">Der Name der Friend-Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut darf nicht den starken Namen der Assembly sein *B*: enthalten nicht die Assemblyversion, Kultur, Architektur oder Token des öffentlichen Schlüssels.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="987f8-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="987f8-122">Wenn Assembly *ein* ist nicht sicher mit dem Namen, den Namen der Friend-Assembly sollte nur den Assemblynamen bestehen.</span><span class="sxs-lookup"><span data-stu-id="987f8-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="987f8-123">Weitere Informationen finden Sie unter [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="987f8-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="987f8-124">Wenn Assembly *B* ist stark benannt, geben Sie den Schlüssel mit starkem Namen für die Assembly *B* mithilfe der projekteinstellung oder der Befehlszeile `/keyfile` (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="987f8-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="987f8-125">Weitere Informationen finden Sie unter [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="987f8-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="987f8-126">Die <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse bietet auch die Möglichkeit zur Freigabe von Typen, mit den folgenden unterschieden:</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="987f8-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="987f8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission>gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="987f8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="987f8-128">Wenn es Hunderte von Typen in der Assembly gibt *ein* , die Sie für die Assembly freigeben möchten *B*, müssen Sie hinzufügen <xref:System.Security.Permissions.StrongNameIdentityPermission>Alle.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="987f8-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="987f8-129">Wenn Sie eine Friend-Assembly verwenden, müssen Sie nur einmal Deklarieren von Friend-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="987f8-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="987f8-130">Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission>, die Typen, die Sie freigeben möchten, müssen als öffentlich deklariert werden.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="987f8-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="987f8-131">Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als deklariert `Friend`.</span><span class="sxs-lookup"><span data-stu-id="987f8-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="987f8-132">Informationen zum Zugreifen auf einer Assemblys `Friend` Typen und Methoden aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule) finden Sie unter [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="987f8-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987f8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="987f8-133">See Also</span></span>  
 <span data-ttu-id="987f8-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="987f8-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="987f8-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="987f8-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></span></span>   
<span data-ttu-id="987f8-136"> [Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="987f8-136"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="987f8-137"> [Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="987f8-137"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="987f8-138"> [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="987f8-138"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="987f8-139"> [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="987f8-139"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
