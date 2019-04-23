---
title: 'Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)'
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: b80d22aa68a969a5468aa1395195058e47f300c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325201"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="55123-102">Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="55123-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="55123-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit Assemblys mit starken Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="55123-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="55123-104">Beide Assemblys müssen starke Namen erhalten.</span><span class="sxs-lookup"><span data-stu-id="55123-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="55123-105">Obwohl beide Assemblys in diesem Beispiel die gleichen Schlüssel verwenden, können Sie unterschiedliche Schlüssel für zwei Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="55123-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="55123-106">So erstellen Sie eine signierte Assembly und eine Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="55123-106">To create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="55123-107">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="55123-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="55123-108">Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und den öffentlichen Schlüssel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="55123-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="55123-109">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="55123-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1.  <span data-ttu-id="55123-110">Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie ihn in der Datei „FriendAssemblies.snk“:</span><span class="sxs-lookup"><span data-stu-id="55123-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="55123-111">Extrahieren Sie den öffentlichen Schlüssel aus FriendAssemblies.snk, und fügen Sie es in FriendAssemblies.publickey ein:</span><span class="sxs-lookup"><span data-stu-id="55123-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="55123-112">Zeigen Sie den öffentlichen Schlüssel, der in der Datei „FriendAssemblies.publickey“ gespeichert ist:</span><span class="sxs-lookup"><span data-stu-id="55123-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="55123-113">Erstellen Sie eine C#-Datei namens `friend_signed_A` mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="55123-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="55123-114">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="55123-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="55123-115">Das Strong Name-Tool generiert jedes Mal einen neuen öffentlichen Schlüssel, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="55123-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="55123-116">Aus diesem Grund müssen Sie den öffentlichen Schlüssel im folgenden Code durch den öffentlichen Schlüssel ersetzen, den Sie gerade erstellt haben, so wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="55123-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
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
  
4. <span data-ttu-id="55123-117">Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="55123-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5. <span data-ttu-id="55123-118">Erstellen Sie eine C#-Datei mit dem Namen `friend_signed_B`, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="55123-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="55123-119">Da friend_signed_A friend_signed_B als Friend-Assembly angibt, kann der Code in friend_signed_B auf `internal`-Typen und -Member aus friend_signed_A zugreifen.</span><span class="sxs-lookup"><span data-stu-id="55123-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="55123-120">Im Folgenden wird der Code dieser Datei dargestellt:</span><span class="sxs-lookup"><span data-stu-id="55123-120">The file contains the following code.</span></span>  
  
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
  
6. <span data-ttu-id="55123-121">Kompilieren und signieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="55123-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="55123-122">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="55123-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="55123-123">Sie müssen den Namen der Ausgabeassembly (EXE oder DLL) explizit mit der `/out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="55123-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="55123-124">Weitere Informationen finden Sie unter [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="55123-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7. <span data-ttu-id="55123-125">Führen Sie die Datei „friend_signed_B.exe“ aus.</span><span class="sxs-lookup"><span data-stu-id="55123-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="55123-126">Das Programm gibt die Zeichenfolge „Class1.Test“ aus.</span><span class="sxs-lookup"><span data-stu-id="55123-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="55123-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="55123-127">.NET Framework Security</span></span>  
 <span data-ttu-id="55123-128">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="55123-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="55123-129">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="55123-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55123-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55123-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="55123-131">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="55123-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="55123-132">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="55123-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="55123-133">Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="55123-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="55123-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="55123-134">/keyfile</span></span>](../../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="55123-135">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="55123-135">Sn.exe (Strong Name Tool)</span></span>](../../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="55123-136">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="55123-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="55123-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="55123-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
