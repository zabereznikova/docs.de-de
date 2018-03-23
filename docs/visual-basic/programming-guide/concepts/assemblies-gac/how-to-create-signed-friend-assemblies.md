---
title: 'Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)'
ms.custom: ''
ms.date: 03/14/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fd9521a87a985cbdeff1616c3070c822892b6e5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)
Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit Assemblys mit starken Namen verwenden. Beide Assemblys müssen starke Namen erhalten. Obwohl beide Assemblys in diesem Beispiel die gleichen Schlüssel verwenden, können Sie unterschiedliche Schlüssel für zwei Assemblys verwenden.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>So erstellen Sie eine signierte Assembly und eine Friend-Assembly  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und den öffentlichen Schlüssel anzuzeigen. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)][Sn.exe (Strong Name-Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
    1.  Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie ihn in der Datei „FriendAssemblies.snk“:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Extrahieren Sie den öffentlichen Schlüssel aus FriendAssemblies.snk, und fügen Sie es in FriendAssemblies.publickey ein:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Zeigen Sie den öffentlichen Schlüssel, der in der Datei „FriendAssemblies.publickey“ gespeichert ist:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_A` , den folgenden Code enthält. Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um „friend_signed_B“ als Friend-Assembly zu deklarieren.  
  
     Das Strong Name-Tool generiert jedes Mal einen neuen öffentlichen Schlüssel, wenn es ausgeführt wird. Aus diesem Grund müssen Sie den öffentlichen Schlüssel im folgenden Code durch den öffentlichen Schlüssel ersetzen, den Sie gerade erstellt haben, so wie im folgenden Beispiel gezeigt.  
  
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
  
4.  Kompilieren und signieren Sie friend_signed_A mithilfe des folgenden Befehls.  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Erstellen Sie eine Visual Basic-Datei mit dem Namen `friend_signed_B` und den folgenden Code enthält. Da friend_signed_A friend_signed_B als Friend-Assembly angibt, kann der Code in friend_signed_B auf `Friend`-Typen und -Member aus friend_signed_A zugreifen. Im Folgenden wird der Code dieser Datei dargestellt:  
  
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
  
6.  Kompilieren und signieren Sie friend_signed_B, indem Sie den folgenden Befehl verwenden.  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Sie können die Assembly explizit festlegen, mit der `-out` -Compileroption. Weitere Informationen finden Sie unter [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Führen Sie die Datei „friend_signed_B.exe“ aus.  
  
     Das Programm zeigt die Zeichenfolge "Class1.Test".  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>. Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `Friend`-Typen und -Member steuert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Assemblys und der globale Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [-keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [Sn.exe (Strong Name-Tool)] [Sn.exe (Strong Name-Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
