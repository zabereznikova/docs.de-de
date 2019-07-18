---
title: 'Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (C#)'
ms.date: 07/20/2015
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
ms.openlocfilehash: 6bc2d807b3d1cf6c82a9ba6303139b9758581f35
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318233"
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a>Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (C#)
Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>So erstellen Sie eine Assembly und eine Friend-Assembly  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Erstellen Sie eine C#-Datei namens `friend_unsigned_A.` mit dem folgenden Code. Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_unsigned_B“ als Friend-Assembly zu deklarieren.  
  
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
  
3. Kompilieren und signieren Sie „friend_unsigned_A“ mithilfe des folgenden Befehls.  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4. Erstellen Sie eine C#-Datei namens `friend_unsigned_B` mit dem folgenden Code. Da friend_unsigned_A friend_unsigned_B als Friend-Assembly angibt, kann der Code in friend_unsigned_B auf `internal`-Typen und -Member aus friend_unsigned_A zugreifen.  
  
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
  
5. Kompilieren Sie „friend_unsigned_B“ mithilfe des folgenden Befehls.  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Sie müssen den Namen der Ausgabeassembly (EXE oder DLL) explizit mit der `/out`-Compileroption angeben. Weitere Informationen finden Sie unter [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
6. Führen Sie die Datei „friend_unsigned_B.exe“ aus.  
  
     Das Programm druckt zwei Zeichenfolgen: „Class1.Test“ und „Class2.Test“.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>. Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal`-Typen und -Member steuert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assemblys in .NET](../../../../standard/assembly/index.md)
- [Friend-Assemblys](../../../../standard/assembly/friend-assemblies.md)
- [Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)
