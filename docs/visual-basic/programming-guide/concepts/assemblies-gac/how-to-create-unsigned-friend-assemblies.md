---
title: 'Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
ms.openlocfilehash: 4771d0fe116d1532c270cf41b209665d5403a9b8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339176"
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)
Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit unsignierten Assemblys verwenden.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>So erstellen Sie eine Assembly und eine Friend-Assembly  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A.` , die den folgenden Code enthält. Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.  
  
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
  
3. Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4. Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_unsigned_B` , die den folgenden Code enthält. Da friend_unsigned_A friend_unsigned_B als Friend-Assembly angibt, kann der Code in friend_unsigned_B auf `Friend`-Typen und -Member aus friend_unsigned_A zugreifen.  
  
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
  
5. Kompilieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption.  
  
6. Führen Sie die Datei „friend_signed_B.exe“ aus.  
  
     Das Programm zeigt zwei Zeichenfolgen: „Class1.Test“ und „Class2.Test“.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>. Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `Friend`-Typen und -Member steuert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assemblys in .NET](../../../../standard/assembly/index.md)
- [Friend-Assemblys](../../../../standard/assembly/friend-assemblies.md)
- [Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Programmierkonzepte für die Anleitung](../../../../visual-basic/programming-guide/concepts/index.md)
