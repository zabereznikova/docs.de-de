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
# <a name="how-to-create-unsigned-friend-assemblies"></a>Vorgehensweise: Erstellen von unsignierten Friend-Assemblys

Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.

## <a name="create-an-assembly-and-a-friend-assembly"></a>Erstellen einer Assembly und einer Friend-Assembly

1. Öffnen Sie eine Eingabeaufforderung.

2. Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_A*, die den folgenden Code enthält. Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um *friend_unsigned_B* als Friend-Assembly zu deklarieren.

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

3. Kompilieren und signieren Sie *friend_unsigned_A* mithilfe des folgenden Befehls:

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_unsigned_B*, die den folgenden Code enthält. Da *friend_unsigned_A* *friend_unsigned_B* als Friend-Assembly angibt, kann der Code in *friend_unsigned_B* auf `internal` (C#) oder `Friend` (Visual Basic)-Typen und -Member aus *friend_unsigned_A* zugreifen.

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

5. Kompilieren Sie *friend_unsigned_B* mithilfe des folgenden Befehls.

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Sie müssen den Namen der Ausgabeassembly ( *.exe* oder *.dll*) explizit mit der `-out`-Compileroption angeben. Weitere Informationen finden Sie unter [-out (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

6. Führen Sie die Datei *friend_unsigned_B.exe* aus.

   Das Programm gibt zwei Zeichenfolgen aus: **Class1.Test** und **Class2.Test**.

## <a name="net-security"></a>.NET-Sicherheit

Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>. Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`- oder `Friend`-Typen und -Member steuert.

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assemblys in .NET](index.md)
- [Friend-Assemblys](friend.md)
- [Vorgehensweise: Erstellen von signierten Friend-Assemblys](create-signed-friend.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
