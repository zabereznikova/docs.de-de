---
title: 'Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
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
ms.openlocfilehash: a8a7df331c8cd93de45d902cb9b6c67460952c6d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="42028-102">Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42028-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="42028-103">Dieses Beispiel zeigt, wie Sie die Friend-Assemblys mit Assemblys mit starke Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42028-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="42028-104">Beide Assemblys müssen starke Namen erhalten.</span><span class="sxs-lookup"><span data-stu-id="42028-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="42028-105">Obwohl beide Assemblys in diesem Beispiel wird die gleichen Schlüssel verwenden, können Sie verschiedene Schlüssel für zwei Assemblys.</span><span class="sxs-lookup"><span data-stu-id="42028-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="42028-106">Um eine signierte Assembly und eine Friend-Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42028-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="42028-107">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="42028-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="42028-108">Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und seinen öffentlichen Schlüssel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="42028-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="42028-109">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="42028-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="42028-110">Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie es in der Datei FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="42028-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="42028-111">Extrahieren Sie den öffentlichen Schlüssel aus FriendAssemblies.snk, und fügen Sie es in FriendAssemblies.PublicKey ein:</span><span class="sxs-lookup"><span data-stu-id="42028-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="42028-112">Zeigen Sie den öffentlichen Schlüssel in der Datei FriendAssemblies.publickey gespeichert:</span><span class="sxs-lookup"><span data-stu-id="42028-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="42028-113">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A` , die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="42028-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="42028-114">Der Code verwendet die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut Friend_signed_B als Friend-Assembly zu deklarieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="42028-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="42028-115">Strong Name-Tool generiert einen neuen öffentlichen Schlüssel, jedes Mal, wenn er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42028-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="42028-116">Aus diesem Grund müssen Sie den öffentlichen Schlüssel in den folgenden Code mit dem öffentlichen Schlüssel, den Sie gerade erstellt haben, den ersetzen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="42028-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="42028-117">Kompilieren Sie und signieren Sie Friend_signed_A mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="42028-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="42028-118">Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_B` und enthält den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="42028-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="42028-119">Da Friend_signed_B Friend_signed_A als Friend-Assembly angegeben wird, kann der Code in Friend_signed_B zugreifen `Friend` Typen und Member von Friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="42028-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="42028-120">Die Datei enthält den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="42028-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="42028-121">Kompilieren Sie und signieren Sie Friend_signed_B mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="42028-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="42028-122">Der Name der vom Compiler erstellten Assembly muss den Namen der Friend-Assembly übergeben entsprechen die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="42028-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="42028-123">Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="42028-123">You can explicitly set the assembly by using the `/out` compiler option.</span></span> <span data-ttu-id="42028-124">Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="42028-124">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="42028-125">Führen Sie die Datei friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="42028-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="42028-126">Das Programm druckt die Zeichenfolge "Class1.Test".</span><span class="sxs-lookup"><span data-stu-id="42028-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="42028-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="42028-127">.NET Framework Security</span></span>  
 <span data-ttu-id="42028-128">Es gibt ähnlichkeiten zwischen dem <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut und der <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="42028-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="42028-129">Der Hauptunterschied besteht darin, die <xref:System.Security.Permissions.StrongNameIdentityPermission>Sicherheitsberechtigungen verfügen, um einen bestimmten Codeabschnitt ausführen kann angefordert werden, während die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut steuert die Sichtbarkeit der `Friend` Typen und Member.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="42028-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42028-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42028-130">See Also</span></span>  
 <span data-ttu-id="42028-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="42028-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="42028-132"> [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="42028-132"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="42028-133"> [Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="42028-133"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="42028-134"> [Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="42028-134"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="42028-135"> [/ keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="42028-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="42028-136"> [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="42028-136"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="42028-137"> [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="42028-137"> [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
<span data-ttu-id="42028-138"> [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="42028-138"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
