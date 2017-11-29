---
title: 'Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2b2667c60a07a2897a0934d210901042e2e43c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="77d64-102">Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77d64-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="77d64-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="77d64-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="77d64-104">So erstellen Sie eine Assembly und eine Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="77d64-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="77d64-105">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="77d64-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="77d64-106">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A.` , den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="77d64-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="77d64-107">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="77d64-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
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
  
3.  <span data-ttu-id="77d64-108">Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="77d64-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="77d64-109">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_unsigned_B` , den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="77d64-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="77d64-110">Da friend_unsigned_A friend_unsigned_B als Friend-Assembly angibt, kann der Code in friend_unsigned_B auf `Friend`-Typen und -Member aus friend_unsigned_A zugreifen.</span><span class="sxs-lookup"><span data-stu-id="77d64-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
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
  
5.  <span data-ttu-id="77d64-111">Kompilieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="77d64-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="77d64-112">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="77d64-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="77d64-113">Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="77d64-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="77d64-114">Führen Sie die Datei „friend_signed_B.exe“ aus.</span><span class="sxs-lookup"><span data-stu-id="77d64-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="77d64-115">Das Programm druckt zwei Zeichenfolgen: „Class1.Test“ und „Class2.Test“.</span><span class="sxs-lookup"><span data-stu-id="77d64-115">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="77d64-116">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="77d64-116">.NET Framework Security</span></span>  
 <span data-ttu-id="77d64-117">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="77d64-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="77d64-118">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `Friend`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="77d64-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d64-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77d64-119">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="77d64-120">Assemblys und der globale Assemblycache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77d64-120">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="77d64-121">Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77d64-121">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="77d64-122">Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77d64-122">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="77d64-123">Programmierkonzepte für die Anleitung</span><span class="sxs-lookup"><span data-stu-id="77d64-123">Programming Guide Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
