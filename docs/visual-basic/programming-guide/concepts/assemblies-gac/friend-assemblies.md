---
title: Friend-Assemblys (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c6e01ae91b9d5d875bb618993cd9eda82db59399
ms.lasthandoff: 03/13/2017

---
# <a name="friend-assemblies-visual-basic"></a>Friend-Assemblys (Visual Basic)
Ein *Friend-Assembly* ist eine Assembly, die auf einer anderen Assembly zugreifen kann [Freund](../../../../visual-basic/language-reference/modifiers/friend.md) Typen und Member. Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie nicht mehr Typen und Member als öffentlich für sie von anderen Assemblys erfolgen markieren. Dies ist besonders hilfreich, in den folgenden Szenarien:  
  
-   Bei Komponententests, wenn Testcode ausgeführt, in wird eine separate Assembly muss jedoch Zugriff auf Member der zu testenden Assembly, die als markiert sind `Friend`.  
  
-   Wenn Sie entwickeln eine Klassenbibliothek und Ergänzungen der Bibliothek in separate Assemblys enthalten sind, aber erfordern Zugriff auf Elemente in vorhandenen Assemblys, die als markiert sind `Friend`.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut, um eine oder mehrere Friend-Assemblys für eine bestimmte Assembly identifizieren.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Im folgenden Beispiel wird das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribut in Assembly A und Assembly gibt `AssemblyB` als Friend-Assembly.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Dadurch erhält die Assembly `AssemblyB` Zugriff auf alle Typen und Member in der Assembly, die als gekennzeichnete `Friend`.  
  
> [!NOTE]
>  Beim Kompilieren einer Assemblys (Assembly `AssemblyB`), die wird der Zugriff auf interne Typen oder internen Member einer anderen Assembly (Assembly *ein*), müssen Sie den Namen der Ausgabedatei (.exe oder .dll) explizit angeben, mit der **/out** (Compileroption). Dies ist erforderlich, da der Compiler noch nicht den Namen für die Assembly generiert wurde, zu dem Zeitpunkt erstellt wird, die es externen Verweise gebunden werden. Weitere Informationen finden Sie unter [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
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
  
 Nur Assemblys, die Sie explizit angeben, wie Freunde zugreifen können `Friend` Typen und Member. Beispielsweise wird Assembly B ein Freund von Assembly A und Assembly C auf Assembly B, C hat keinen Zugriff auf `Friend` Typen in A.  
  
 Der Compiler führt eine grundlegende Überprüfung der Namen der Friend-Assembly übergeben, um die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Wenn Assembly *ein* deklariert *B* als Friend-Assembly, die Validierungsregeln werden wie folgt:  
  
-   Wenn Assembly *ein* ist stark benannte Assembly *B* muss auch starken Namen. Der Name der Friend-Assembly, die an das Attribut übergeben wird enthalten den Namen der Assembly und der öffentliche Schlüssel des Schlüssel mit starkem Namen, die zum Signieren der Assembly verwendet wird *B*.  
  
     Der Name der Friend-Assembly, die an die <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Attribut darf nicht den starken Namen der Assembly sein *B*: enthalten nicht die Assemblyversion, Kultur, Architektur oder Token des öffentlichen Schlüssels.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
-   Wenn Assembly *ein* ist nicht sicher mit dem Namen, den Namen der Friend-Assembly sollte nur den Assemblynamen bestehen. Weitere Informationen finden Sie unter [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Wenn Assembly *B* ist stark benannt, geben Sie den Schlüssel mit starkem Namen für die Assembly *B* mithilfe der projekteinstellung oder der Befehlszeile `/keyfile` (Compileroption). Weitere Informationen finden Sie unter [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 Die <xref:System.Security.Permissions.StrongNameIdentityPermission>Klasse bietet auch die Möglichkeit zur Freigabe von Typen, mit den folgenden unterschieden:</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission>gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   Wenn es Hunderte von Typen in der Assembly gibt *ein* , die Sie für die Assembly freigeben möchten *B*, müssen Sie hinzufügen <xref:System.Security.Permissions.StrongNameIdentityPermission>Alle.</xref:System.Security.Permissions.StrongNameIdentityPermission> Wenn Sie eine Friend-Assembly verwenden, müssen Sie nur einmal Deklarieren von Friend-Beziehung.  
  
-   Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission>, die Typen, die Sie freigeben möchten, müssen als öffentlich deklariert werden.</xref:System.Security.Permissions.StrongNameIdentityPermission> Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als deklariert `Friend`.  
  
 Informationen zum Zugreifen auf einer Assemblys `Friend` Typen und Methoden aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule) finden Sie unter [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [Gewusst wie: Erstellen von unsignierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [Gewusst wie: Erstellen von signierten Friend-Assemblys (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
