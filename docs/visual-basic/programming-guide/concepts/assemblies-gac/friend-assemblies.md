---
title: Friend-Assemblys (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
ms.openlocfilehash: efb22ce25bdd39fd7a511503eb3ff6792639d29e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579796"
---
# <a name="friend-assemblies-visual-basic"></a>Friend-Assemblys (Visual Basic)
Ein *Friend-Assembly* ist eine Assembly, die auf einer anderen Assembly zugreifen kann [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) Typen und Member. Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können. Dies ist insbesondere in folgenden Szenarios nützlich:  
  
-   Während der Komponententests ausgeführt werden, wenn Testcode ausgeführt, in wird eine separate Assembly erfordert jedoch Zugriff auf Elemente in der getesteten Assembly, die als markiert sind `Friend`.  
  
-   Wenn Sie eine Klassenbibliothek entwickeln und Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, jedoch benötigen Sie Zugriff auf Member in vorhandenen Assemblys, die als markiert sind `Friend`.  
  
## <a name="remarks"></a>Hinweise  
 Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren. Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in Assembly A verwendet, und Assembly `AssemblyB` wird als Friend-Assembly angegeben. Dadurch erhält Assembly `AssemblyB` Zugriff auf alle Typen und Member in Assembly A, die als `Friend` markiert sind.  
  
> [!NOTE]
>  Beim Kompilieren einer Assembly (Assembly `AssemblyB`), die auf interne Typen oder interne Member einer anderen Assembly (Assembly *A*) zugreift, müssen Sie den Namen der Ausgabedatei (.exe oder .dll) mit der Compileroption **/out** explizit angeben. Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt. Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
```  
  
 Nur Assemblys, die Sie explizit als Friends angeben, können auf `Friend`-Typen und -Member zugreifen. Wenn zum Beispiel Assembly B ein Friend von Assembly A ist und Assembly C auf Assembly B verweist, hat C keinen Zugriff auf `Friend`-Typen in A.  
  
 Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Wenn Assembly *A* Assembly *B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:  
  
-   Wenn Assembly *A* einen starken Namen hat, muss Assembly *B* auch einen starken Namen haben. Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von Assembly *B* verwendet wird.  
  
     Der Name der Friend-Assembly, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird, darf nicht der starke Name von Assembly *B* sein: Er darf nicht die Assemblyversion, Kultur, Architektur oder das Token des öffentlichen Schlüssels enthalten.  
  
-   Wenn Assembly *A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Wenn Assembly *B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für Assembly *B* über die Projekteinstellung oder bei Verwendung der Befehlszeile die Compileroption `/keyfile` angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.  
  
-   Wenn es Hunderte von Typen in Assembly *A* gibt, die Sie für Assembly *B* freigeben möchten, müssen Sie allen <xref:System.Security.Permissions.StrongNameIdentityPermission> hinzufügen. Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.  
  
-   Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden. Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als `Friend` deklariert.  
  
 Informationen zur Verwendung auf einer Assembly `Friend` Typen und Methoden aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule), finden Sie unter [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [Vorgehensweise: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Assemblys und der globale Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
