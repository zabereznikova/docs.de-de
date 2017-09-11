---
title: 'Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)'
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
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
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
ms.openlocfilehash: e9d56602eaffe73ff301ade95aaebeabab663be6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="31281-102">Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="31281-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="31281-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit Assemblys mit starken Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="31281-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="31281-104">Beide Assemblys müssen starke Namen erhalten.</span><span class="sxs-lookup"><span data-stu-id="31281-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="31281-105">Obwohl beide Assemblys in diesem Beispiel die gleichen Schlüssel verwenden, können Sie unterschiedliche Schlüssel für zwei Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="31281-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="31281-106">So erstellen Sie eine signierte Assembly und eine Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="31281-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="31281-107">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="31281-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="31281-108">Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und den öffentlichen Schlüssel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31281-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="31281-109">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="31281-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="31281-110">Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie ihn in der Datei „FriendAssemblies.snk“:</span><span class="sxs-lookup"><span data-stu-id="31281-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="31281-111">Extrahieren Sie den öffentlichen Schlüssel aus FriendAssemblies.snk, und fügen Sie es in FriendAssemblies.publickey ein:</span><span class="sxs-lookup"><span data-stu-id="31281-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="31281-112">Zeigen Sie den öffentlichen Schlüssel, der in der Datei „FriendAssemblies.publickey“ gespeichert ist:</span><span class="sxs-lookup"><span data-stu-id="31281-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="31281-113">Erstellen Sie eine C#-Datei namens `friend_signed_A` mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="31281-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="31281-114">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="31281-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="31281-115">Das Strong Name-Tool generiert jedes Mal einen neuen öffentlichen Schlüssel, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31281-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="31281-116">Aus diesem Grund müssen Sie den öffentlichen Schlüssel im folgenden Code durch den öffentlichen Schlüssel ersetzen, den Sie gerade erstellt haben, so wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="31281-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="31281-117">Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="31281-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5.  <span data-ttu-id="31281-118">Erstellen Sie eine C#-Datei mit dem Namen `friend_signed_B`, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="31281-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="31281-119">Da friend_signed_A friend_signed_B als Friend-Assembly angibt, kann der Code in friend_signed_B auf `internal`-Typen und -Member aus friend_signed_A zugreifen.</span><span class="sxs-lookup"><span data-stu-id="31281-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="31281-120">Im Folgenden wird der Code dieser Datei dargestellt:</span><span class="sxs-lookup"><span data-stu-id="31281-120">The file contains the following code.</span></span>  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="31281-121">Kompilieren und signieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="31281-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="31281-122">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="31281-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="31281-123">Sie müssen den Namen der Ausgabeassembly (EXE oder DLL) explizit mit der `/out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="31281-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="31281-124">Weitere Informationen finden Sie unter [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="31281-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7.  <span data-ttu-id="31281-125">Führen Sie die Datei „friend_signed_B.exe“ aus.</span><span class="sxs-lookup"><span data-stu-id="31281-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="31281-126">Das Programm gibt die Zeichenfolge „Class1.Test“ aus.</span><span class="sxs-lookup"><span data-stu-id="31281-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="31281-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="31281-127">.NET Framework Security</span></span>  
 <span data-ttu-id="31281-128">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="31281-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="31281-129">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="31281-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31281-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31281-130">See Also</span></span>  
 <span data-ttu-id="31281-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="31281-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="31281-132">[Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="31281-132">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 <span data-ttu-id="31281-133">[Friend Assemblies (C#) (Friend-Assemblys (C#))](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="31281-133">[Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
 <span data-ttu-id="31281-134">[How to: Create Unsigned Friend Assemblies (C#) (Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#))](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="31281-134">[How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
 <span data-ttu-id="31281-135">[/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="31281-135">[/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
 <span data-ttu-id="31281-136">[Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="31281-136">[Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
 <span data-ttu-id="31281-137">[Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="31281-137">[Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
 [<span data-ttu-id="31281-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="31281-138">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)

