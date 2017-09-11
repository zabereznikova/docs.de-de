---
title: 'Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d184b5d6f8334df46351d3f2974f1fb91e54a492
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="3a81e-102">Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a81e-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="3a81e-103">Dieses Beispiel zeigt die Verwendung von Friend-Assemblys mit Assemblys, die nicht signiert sind.</span><span class="sxs-lookup"><span data-stu-id="3a81e-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="3a81e-104">Um eine Assembly und eine Friend-Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a81e-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="3a81e-105">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="3a81e-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="3a81e-106">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A.` , die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="3a81e-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="3a81e-107">Der Code verwendet die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut Friend_signed_B als Friend-Assembly zu deklarieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="3a81e-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
    <Assembly: InternalsVisibleTo("friend_unsigned_B")>   
  
    ' Friend type.  
    Friend Class Class1  
        Public Sub Test()  
            Console.WriteLine("Class1.Test")  
        End Sub  
    End Class  
  
    ' Public type with Friend member.  
    Public Class Class2  
        Friend Sub Test()  
            Console.WriteLine("Class2.Test")  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="3a81e-108">Kompilieren Sie und signieren Sie Friend_signed_A mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="3a81e-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="3a81e-109">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_unsigned_B` , die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="3a81e-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="3a81e-110">Da gekennzeichneten friend_unsigned_A als Friend-Assembly angegeben wird, kann der Code in Friend_unsigned_B zugreifen `Friend` Typen und Member aus gekennzeichneten.</span><span class="sxs-lookup"><span data-stu-id="3a81e-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    Module Module1  
        Sub Main()  
            ' Access a Friend type.  
            Dim inst1 As New Class1()  
            inst1.Test()  
  
            Dim inst2 As New Class2()  
            ' Access a Friend member of a public type.  
            inst2.Test()  
  
            System.Console.ReadLine()  
        End Sub  
    End Module  
    ```  
  
5.  <span data-ttu-id="3a81e-111">Kompilieren Sie Friend_signed_B mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="3a81e-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="3a81e-112">Der Namen der Assembly, die vom Compiler generiert wird, muss der Name der Friend-Assembly, die an entsprechen den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="3a81e-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="3a81e-113">Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="3a81e-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="3a81e-114">Führen Sie die Datei friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="3a81e-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="3a81e-115">Das Programm druckt zwei Zeichenfolgen: "Class1.Test" und "Class2.Test".</span><span class="sxs-lookup"><span data-stu-id="3a81e-115">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3a81e-116">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3a81e-116">.NET Framework Security</span></span>  
 <span data-ttu-id="3a81e-117">Es gibt ähnlichkeiten zwischen dem <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut und der <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="3a81e-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="3a81e-118">Der Hauptunterschied besteht darin, die <xref:System.Security.Permissions.StrongNameIdentityPermission>Sicherheitsberechtigungen verfügen, um einen bestimmten Codeabschnitt ausführen kann angefordert werden, während die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut steuert die Sichtbarkeit der `Friend` Typen und Member.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="3a81e-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a81e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a81e-119">See Also</span></span>  
 <span data-ttu-id="3a81e-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="3a81e-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="3a81e-121"> [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a81e-121"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="3a81e-122"> [Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="3a81e-122"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="3a81e-123"> [Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="3a81e-123"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="3a81e-124"> [Programmierkonzepte für die Anleitung](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="3a81e-124"> [Programming Guide Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
