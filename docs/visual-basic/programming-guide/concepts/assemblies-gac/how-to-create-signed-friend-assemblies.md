---
title: 'Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1a69f7e833800ec7417bc35fad763f1001b3e7f9
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)
Dieses Beispiel zeigt, wie Sie die Friend-Assemblys mit Assemblys mit starke Namen verwendet werden. Beide Assemblys müssen starke Namen erhalten. Obwohl beide Assemblys in diesem Beispiel wird die gleichen Schlüssel verwenden, können Sie verschiedene Schlüssel für zwei Assemblys.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Um eine signierte Assembly und eine Friend-Assembly zu erstellen.  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und seinen öffentlichen Schlüssel anzeigen. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
    1.  Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie es in der Datei FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Extrahieren Sie den öffentlichen Schlüssel aus FriendAssemblies.snk, und fügen Sie es in FriendAssemblies.PublicKey ein:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Zeigen Sie den öffentlichen Schlüssel in der Datei FriendAssemblies.publickey gespeichert:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A` , die den folgenden Code enthält. Der Code verwendet die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut Friend_signed_B als Friend-Assembly zu deklarieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
     Strong Name-Tool generiert einen neuen öffentlichen Schlüssel, jedes Mal, wenn er ausgeführt wird. Aus diesem Grund müssen Sie den öffentlichen Schlüssel in den folgenden Code mit dem öffentlichen Schlüssel, den Sie gerade erstellt haben, den ersetzen, wie im folgenden Beispiel gezeigt.  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  Kompilieren Sie und signieren Sie Friend_signed_A mit dem folgenden Befehl.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_B` und enthält den folgenden Code. Da Friend_signed_B Friend_signed_A als Friend-Assembly angegeben wird, kann der Code in Friend_signed_B zugreifen `Friend` Typen und Member von Friend_signed_A. Die Datei enthält den folgenden Code.  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  Kompilieren Sie und signieren Sie Friend_signed_B mit dem folgenden Befehl.  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     Der Name der vom Compiler erstellten Assembly muss den Namen der Friend-Assembly übergeben entsprechen die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Sie können die Assembly explizit festlegen, mit der `/out` -Compileroption. Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Führen Sie die Datei friend_signed_B.exe.  
  
     Das Programm druckt die Zeichenfolge "Class1.Test".  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es gibt ähnlichkeiten zwischen dem <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut und der <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Der Hauptunterschied besteht darin, die <xref:System.Security.Permissions.StrongNameIdentityPermission>Sicherheitsberechtigungen verfügen, um einen bestimmten Codeabschnitt ausführen kann angefordert werden, während die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut steuert die Sichtbarkeit der `Friend` Typen und Member.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [/ keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617)   
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
