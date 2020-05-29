---
title: 'Vorgehensweise: Erstellen von unsignierten Friend-Assemblys'
description: Dieser Artikel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden. Er enthält Informationen zur .NET-Sicherheit.
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8d3e13669c36048759fedeb3df1bfb59fd476317
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378972"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="91fea-104">Vorgehensweise: Erstellen von unsignierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="91fea-104">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="91fea-105">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="91fea-105">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="91fea-106">Erstellen einer Assembly und einer Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="91fea-106">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="91fea-107">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="91fea-107">Open a command prompt.</span></span>

2. <span data-ttu-id="91fea-108">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_A*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="91fea-108">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="91fea-109">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um *friend_unsigned_B* als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="91fea-109">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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

3. <span data-ttu-id="91fea-110">Kompilieren und signieren Sie *friend_unsigned_A* mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="91fea-110">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="91fea-111">Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_B*, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="91fea-111">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="91fea-112">Da *friend_unsigned_A* *friend_unsigned_B* als Friend-Assembly angibt, kann der Code in *friend_unsigned_B* auf `internal` (C#) oder `Friend` (Visual Basic)-Typen und -Member aus *friend_unsigned_A* zugreifen.</span><span class="sxs-lookup"><span data-stu-id="91fea-112">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="91fea-113">Kompilieren Sie *friend_unsigned_B* mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="91fea-113">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="91fea-114">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="91fea-114">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="91fea-115">Sie müssen den Namen der Ausgabeassembly ( *.exe* oder *.dll*) explizit mit der `-out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="91fea-115">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="91fea-116">Weitere Informationen finden Sie unter [-out (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-116">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="91fea-117">Führen Sie die Datei *friend_unsigned_B.exe* aus.</span><span class="sxs-lookup"><span data-stu-id="91fea-117">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="91fea-118">Das Programm gibt zwei Zeichenfolgen aus: **Class1.Test** und **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="91fea-118">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="91fea-119">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="91fea-119">.NET security</span></span>

<span data-ttu-id="91fea-120">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="91fea-120">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="91fea-121">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`- oder `Friend`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="91fea-121">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="91fea-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91fea-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="91fea-123">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="91fea-123">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="91fea-124">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="91fea-124">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="91fea-125">How to: Erstellen von signierten Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="91fea-125">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="91fea-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="91fea-126">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="91fea-127">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91fea-127">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
