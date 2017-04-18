---
title: 'Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ceddb35c306f72c8927deda326d9fcca6c75d786
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)
Dieses Beispiel zeigt die Verwendung von Friend-Assemblys mit Assemblys, die nicht signiert sind.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Um eine Assembly und eine Friend-Assembly zu erstellen.  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A.` , die den folgenden Code enthält. Der Code verwendet die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut Friend_signed_B als Friend-Assembly zu deklarieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
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
  
3.  Kompilieren Sie und signieren Sie Friend_signed_A mit dem folgenden Befehl.  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_unsigned_B` , die den folgenden Code enthält. Da gekennzeichneten friend_unsigned_A als Friend-Assembly angegeben wird, kann der Code in Friend_unsigned_B zugreifen `Friend` Typen und Member aus gekennzeichneten.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
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
  
5.  Kompilieren Sie Friend_signed_B mit dem folgenden Befehl.  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Der Namen der Assembly, die vom Compiler generiert wird, muss der Name der Friend-Assembly, die an entsprechen den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption.  
  
6.  Führen Sie die Datei friend_signed_B.exe.  
  
     Das Programm druckt zwei Zeichenfolgen: "Class1.Test" und "Class2.Test".  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es gibt ähnlichkeiten zwischen dem <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut und der <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Der Hauptunterschied besteht darin, die <xref:System.Security.Permissions.StrongNameIdentityPermission>Sicherheitsberechtigungen verfügen, um einen bestimmten Codeabschnitt ausführen kann angefordert werden, während die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut steuert die Sichtbarkeit der `Friend` Typen und Member.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Programmierkonzepte für die Anleitung](../../../../visual-basic/programming-guide/concepts/index.md)
