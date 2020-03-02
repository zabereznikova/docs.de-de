---
title: 'Vorgehensweise: Erstellen von signierten Friend-Assemblys'
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9912fa70014a8828e994cf528644aaa7cb351fea
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159493"
---
# <a name="how-to-create-signed-friend-assemblies"></a><span data-ttu-id="9eee1-102">Vorgehensweise: Erstellen von signierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="9eee1-102">How to: Create signed friend assemblies</span></span>
<span data-ttu-id="9eee1-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit Assemblys mit starken Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eee1-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="9eee1-104">Beide Assemblys müssen starke Namen erhalten.</span><span class="sxs-lookup"><span data-stu-id="9eee1-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="9eee1-105">Obwohl beide Assemblys in diesem Beispiel die gleichen Schlüssel verwenden, können Sie unterschiedliche Schlüssel für zwei Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eee1-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="9eee1-106">Erstellen einer signierte Assembly und einer Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="9eee1-106">Create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="9eee1-107">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="9eee1-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="9eee1-108">Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und den öffentlichen Schlüssel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9eee1-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="9eee1-109">Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="9eee1-109">For more information, see [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="9eee1-110">Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie ihn in der Datei *FriendAssemblies.snk*:</span><span class="sxs-lookup"><span data-stu-id="9eee1-110">Generate a strong-name key for this example and store it in the file *FriendAssemblies.snk*:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="9eee1-111">Extrahieren Sie den öffentlichen Schlüssel aus *FriendAssemblies.snk*, und fügen Sie ihn in *FriendAssemblies.publickey* ein:</span><span class="sxs-lookup"><span data-stu-id="9eee1-111">Extract the public key from *FriendAssemblies.snk* and put it into *FriendAssemblies.publickey*:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="9eee1-112">Zeigen Sie den öffentlichen Schlüssel, der in der Datei *FriendAssemblies.publickey* gespeichert ist:</span><span class="sxs-lookup"><span data-stu-id="9eee1-112">Display the public key stored in the file *FriendAssemblies.publickey*:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="9eee1-113">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_signed_A*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="9eee1-113">Create a C# or Visual Basic file named *friend_signed_A* that contains the following code.</span></span> <span data-ttu-id="9eee1-114">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um *friend_signed_B* als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9eee1-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_signed_B* as a friend assembly.</span></span>  

   <span data-ttu-id="9eee1-115">Das Strong Name-Tool generiert jedes Mal einen neuen öffentlichen Schlüssel, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9eee1-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="9eee1-116">Aus diesem Grund müssen Sie den öffentlichen Schlüssel im folgenden Code durch den öffentlichen Schlüssel ersetzen, den Sie gerade erstellt haben, so wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9eee1-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  

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

   ```vb  
   ' friend_signed_A.vb  
   ' Compile with:
   ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   Imports System.Runtime.CompilerServices  

   <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>
   Public Class Class1  
       Public Sub Test()  
           System.Console.WriteLine("Class1.Test")  
           System.Console.ReadLine()  
       End Sub  
   End Class  
   ```  

4. <span data-ttu-id="9eee1-117">Kompilieren und signieren Sie *friend_signed_A* mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="9eee1-117">Compile and sign *friend_signed_A* by using the following command.</span></span>  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. <span data-ttu-id="9eee1-118">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_signed_B*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="9eee1-118">Create a C# or Visual Basic file named *friend_signed_B* that contains the following code.</span></span> <span data-ttu-id="9eee1-119">Da *friend_signed_A* *friend_signed_B* als Friend-Assembly angibt, kann der Code in *friend_signed_B* auf `internal` (C#)- oder `Friend`-Typen und -Member (Visual Basic) aus *friend_signed_A* zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9eee1-119">Because *friend_signed_A* specifies *friend_signed_B* as a friend assembly, the code in *friend_signed_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_signed_A*.</span></span> <span data-ttu-id="9eee1-120">Im Folgenden wird der Code dieser Datei dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9eee1-120">The file contains the following code.</span></span>  

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

   ```vb  
   ' friend_signed_B.vb  
   ' Compile with:
   ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   Module Sample  
       Public Sub Main()  
           Dim inst As New Class1  
           inst.Test()  
       End Sub  
   End Module  
   ```  

6. <span data-ttu-id="9eee1-121">Kompilieren und signieren Sie *friend_signed_B*, indem Sie den folgenden Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eee1-121">Compile and sign *friend_signed_B* by using the following command.</span></span>  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   <span data-ttu-id="9eee1-122">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9eee1-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="9eee1-123">Sie müssen den Namen der Ausgabeassembly ( *.exe* oder *.dll*) explizit mit der `-out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="9eee1-123">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="9eee1-124">Weitere Informationen finden Sie unter [-out (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="9eee1-124">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>  

7. <span data-ttu-id="9eee1-125">Führen Sie die Datei *friend_signed_B.exe* aus.</span><span class="sxs-lookup"><span data-stu-id="9eee1-125">Run the *friend_signed_B.exe* file.</span></span>  

   <span data-ttu-id="9eee1-126">Das Programm gibt die Zeichenfolge **Class1.Test** aus.</span><span class="sxs-lookup"><span data-stu-id="9eee1-126">The program outputs the string **Class1.Test**.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="9eee1-127">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9eee1-127">.NET security</span></span>  
 <span data-ttu-id="9eee1-128">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="9eee1-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="9eee1-129">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal` (C#)- oder `Friend` (Visual Basic)-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="9eee1-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eee1-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eee1-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="9eee1-131">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="9eee1-131">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="9eee1-132">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="9eee1-132">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="9eee1-133">How to: Erstellen von unsignierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="9eee1-133">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="9eee1-134">-keyfile (C#)</span><span class="sxs-lookup"><span data-stu-id="9eee1-134">-keyfile (C#)</span></span>](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="9eee1-135">-keyfile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eee1-135">-keyfile (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="9eee1-136">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="9eee1-136">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="9eee1-137">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="9eee1-137">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="9eee1-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9eee1-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9eee1-139">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eee1-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
