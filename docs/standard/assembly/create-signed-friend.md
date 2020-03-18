---
title: 'Vorgehensweise: Erstellen von signierten Friend-Assemblys'
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9912fa70014a8828e994cf528644aaa7cb351fea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159493"
---
# <a name="how-to-create-signed-friend-assemblies"></a>Vorgehensweise: Erstellen von signierten Friend-Assemblys
Dieses Beispiel zeigt, wie Sie Friend-Assemblys mit Assemblys mit starken Namen verwenden. Beide Assemblys müssen starke Namen erhalten. Obwohl beide Assemblys in diesem Beispiel die gleichen Schlüssel verwenden, können Sie unterschiedliche Schlüssel für zwei Assemblys verwenden.  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a>Erstellen einer signierte Assembly und einer Friend-Assembly  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Verwenden Sie die folgende Sequenz von Befehlen mit dem Strong Name-Tool, um eine Schlüsseldatei zu generieren und den öffentlichen Schlüssel anzuzeigen. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md).  
  
    1. Generieren Sie einen Schlüssel mit starkem Namen für dieses Beispiel, und speichern Sie ihn in der Datei *FriendAssemblies.snk*:  
  
         `sn -k FriendAssemblies.snk`  
  
    2. Extrahieren Sie den öffentlichen Schlüssel aus *FriendAssemblies.snk*, und fügen Sie ihn in *FriendAssemblies.publickey* ein:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. Zeigen Sie den öffentlichen Schlüssel, der in der Datei *FriendAssemblies.publickey* gespeichert ist:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_signed_A*, die den folgenden Code enthält. Der Code verwendet das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, um *friend_signed_B* als Friend-Assembly zu deklarieren.  

   Das Strong Name-Tool generiert jedes Mal einen neuen öffentlichen Schlüssel, wenn es ausgeführt wird. Aus diesem Grund müssen Sie den öffentlichen Schlüssel im folgenden Code durch den öffentlichen Schlüssel ersetzen, den Sie gerade erstellt haben, so wie im folgenden Beispiel gezeigt.  

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

4. Kompilieren und signieren Sie *friend_signed_A* mithilfe des folgenden Befehls.  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. Erstellen Sie eine C#- oder eine Visual Basic-Datei mit dem Namen *friend_signed_B*, die den folgenden Code enthält. Da *friend_signed_A* *friend_signed_B* als Friend-Assembly angibt, kann der Code in *friend_signed_B* auf `internal` (C#)- oder `Friend`-Typen und -Member (Visual Basic) aus *friend_signed_A* zugreifen. Im Folgenden wird der Code dieser Datei dargestellt:  

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

6. Kompilieren und signieren Sie *friend_signed_B*, indem Sie den folgenden Befehl verwenden.  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   Der Name der vom Compiler generierten Assembly muss mit dem Namen der Friend-Assembly übereinstimmen, die an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Sie müssen den Namen der Ausgabeassembly ( *.exe* oder *.dll*) explizit mit der `-out`-Compileroption angeben. Weitere Informationen finden Sie unter [-out (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).  

7. Führen Sie die Datei *friend_signed_B.exe* aus.  

   Das Programm gibt die Zeichenfolge **Class1.Test** aus.  
  
## <a name="net-security"></a>.NET-Sicherheit  
 Es gibt Ähnlichkeiten zwischen dem Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> und der Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission>. Der Hauptunterschied besteht darin, dass <xref:System.Security.Permissions.StrongNameIdentityPermission> Sicherheitsberechtigungen verlangen kann, um einen bestimmten Codeabschnitt auszuführen, während das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> die Sichtbarkeit der `internal` (C#)- oder `Friend` (Visual Basic)-Typen und -Member steuert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assemblys in .NET](index.md)
- [Friend-Assemblys](friend.md)
- [How to: Erstellen von unsignierten Friend-Assemblys](create-unsigned-friend.md)
- [-keyfile (C#)](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [-keyfile (Visual Basic)](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Sn.exe (Strong Name-Tool)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
