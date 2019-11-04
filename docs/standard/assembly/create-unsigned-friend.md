---
title: 'Vorgehensweise: Erstellen von unsignierten Friend-Assemblys'
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: d8fdc3061067d85498dc5bbed7bf324f99169a36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774347"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="486c4-102">Vorgehensweise: Erstellen von unsignierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="486c4-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="486c4-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="486c4-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="486c4-104">Erstellen einer Assembly und einer Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="486c4-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="486c4-105">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="486c4-105">Open a command prompt.</span></span>

2. <span data-ttu-id="486c4-106">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_A*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="486c4-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="486c4-107">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um *friend_unsigned_B* als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="486c4-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
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

3. <span data-ttu-id="486c4-108">Kompilieren und signieren Sie *friend_unsigned_A* mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="486c4-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="486c4-109">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_B*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="486c4-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="486c4-110">Da *friend_unsigned_A* *friend_unsigned_B* als Friend-Assembly angibt, kann der Code in *friend_unsigned_B* auf `internal` (C#) oder `Friend` (Visual Basic)-Typen und -Member aus *friend_unsigned_A* zugreifen.</span><span class="sxs-lookup"><span data-stu-id="486c4-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
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

5. <span data-ttu-id="486c4-111">Kompilieren Sie *friend_unsigned_B* mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="486c4-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="486c4-112">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="486c4-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="486c4-113">Sie müssen den Namen der Ausgabeassembly ( *.exe* oder *.dll*) explizit mit der `-out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="486c4-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="486c4-114">Weitere Informationen finden Sie unter [-out (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="486c4-114">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="486c4-115">Führen Sie die Datei *friend_unsigned_B.exe* aus.</span><span class="sxs-lookup"><span data-stu-id="486c4-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="486c4-116">Das Programm gibt zwei Zeichenfolgen aus: **Class1.Test** und **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="486c4-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="486c4-117">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="486c4-117">.NET security</span></span>

<span data-ttu-id="486c4-118">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="486c4-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="486c4-119">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`- oder `Friend`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="486c4-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="486c4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="486c4-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="486c4-121">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="486c4-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="486c4-122">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="486c4-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="486c4-123">Vorgehensweise: Erstellen von signierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="486c4-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="486c4-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="486c4-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="486c4-125">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="486c4-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
