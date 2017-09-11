---
title: 'Vorgehensweise: Erstellen von nicht signierten Friend-Assemblys (C#)'
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
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
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
ms.openlocfilehash: 967436204ab0824a510c12dc4c6e288d91d7dfa0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a><span data-ttu-id="840cd-102">Vorgehensweise: Erstellen von nicht signierten Friend-Assemblys (C#)</span><span class="sxs-lookup"><span data-stu-id="840cd-102">How to: Create Unsigned Friend Assemblies (C#)</span></span>
<span data-ttu-id="840cd-103">Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="840cd-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="840cd-104">So erstellen Sie eine Assembly und eine Friend-Assembly</span><span class="sxs-lookup"><span data-stu-id="840cd-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="840cd-105">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="840cd-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="840cd-106">Erstellen Sie eine C#-Datei namens `friend_signed_A.` mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="840cd-106">Create a C# file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="840cd-107">Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="840cd-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
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
  
3.  <span data-ttu-id="840cd-108">Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="840cd-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4.  <span data-ttu-id="840cd-109">Erstellen Sie eine C#-Datei namens `friend_unsigned_B` mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="840cd-109">Create a C# file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="840cd-110">Da friend_unsigned_A friend_unsigned_B als Friend-Assembly angibt, kann der Code in friend_unsigned_B auf `internal`-Typen und -Member aus friend_unsigned_A zugreifen.</span><span class="sxs-lookup"><span data-stu-id="840cd-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `internal` types and members from friend_unsigned_A.</span></span>  
  
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
  
5.  <span data-ttu-id="840cd-111">Kompilieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="840cd-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     <span data-ttu-id="840cd-112">Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="840cd-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="840cd-113">Sie müssen den Namen der Ausgabeassembly (EXE oder DLL) explizit mit der `/out`-Compileroption angeben.</span><span class="sxs-lookup"><span data-stu-id="840cd-113">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span> <span data-ttu-id="840cd-114">Weitere Informationen finden Sie unter [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="840cd-114">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
6.  <span data-ttu-id="840cd-115">Führen Sie die Datei „friend_signed_B.exe“ aus.</span><span class="sxs-lookup"><span data-stu-id="840cd-115">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="840cd-116">Das Programm druckt zwei Zeichenfolgen: „Class1.Test“ und „Class2.Test“.</span><span class="sxs-lookup"><span data-stu-id="840cd-116">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="840cd-117">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="840cd-117">.NET Framework Security</span></span>  
 <span data-ttu-id="840cd-118">Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="840cd-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="840cd-119">Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`-Typen und -Member steuert.</span><span class="sxs-lookup"><span data-stu-id="840cd-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="840cd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="840cd-120">See Also</span></span>  
 <span data-ttu-id="840cd-121"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="840cd-121"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="840cd-122">[Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="840cd-122">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 <span data-ttu-id="840cd-123">[Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="840cd-123">[Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
 <span data-ttu-id="840cd-124">[Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="840cd-124">[How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
 [<span data-ttu-id="840cd-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="840cd-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)

