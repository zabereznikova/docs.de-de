---
title: Friend-Assemblys (C#)
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
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
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
ms.openlocfilehash: e2680b5799c552a063ff7c539a31a5dd00b90a75
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="friend-assemblies-c"></a>Friend-Assemblys (C#)
Eine *Friend-Assembly* ist eine Assembly, die auf die [internen](../../../../csharp/language-reference/keywords/internal.md) Typen und Member einer anderen Assembly zugreifen kann. Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können. Dies ist insbesondere in folgenden Szenarios nützlich:  
  
-   Wenn der Testcode bei Komponententests in einer separaten Assembly ausgeführt wird, aber Zugriff auf Member in der getesteten Assembly benötigt, die als `internal` markiert sind.  
  
-   Wenn beim Entwickeln einer Klassenbibliothek die Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, aber Zugriff auf Member in vorhandenen Assemblys erfordern, die als `internal` markiert sind.  
  
## <a name="remarks"></a>Hinweise  
 Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren. Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in Assembly A verwendet, und Assembly `AssemblyB` wird als Friend-Assembly angegeben. Dadurch erhält Assembly `AssemblyB` Zugriff auf alle Typen und Member in Assembly A, die als `internal` markiert sind.  
  
> [!NOTE]
>  Beim Kompilieren einer Assembly (Assembly `AssemblyB`), die auf interne Typen oder interne Member einer anderen Assembly (Assembly *A*) zugreift, müssen Sie den Namen der Ausgabedatei (.exe oder .dll) mit der Compileroption **/out** explizit angeben. Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt. Weitere Informationen finden Sie unter [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
```csharp  
using System.Runtime.CompilerServices;  
using System;  
  
[assembly: InternalsVisibleTo("AssemblyB")]  
  
// The class is internal by default.  
class FriendClass  
{  
    public void Test()  
    {  
        Console.WriteLine("Sample Class");  
    }  
}  
  
// Public class that has an internal method.  
public class ClassWithFriendMethod  
{  
    internal void Test()  
    {  
        Console.WriteLine("Sample Method");  
    }  
  
}  
```  
  
 Nur Assemblys, die Sie explizit als Friends angeben, können auf `internal`-Typen und -Member zugreifen. Wenn zum Beispiel Assembly B ein Friend von Assembly A ist und Assembly C auf Assembly B verweist, hat C keinen Zugriff auf `internal`-Typen in A.  
  
 Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Wenn Assembly *A* Assembly *B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:  
  
-   Wenn Assembly *A* einen starken Namen hat, muss Assembly *B* auch einen starken Namen haben. Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von Assembly *B* verwendet wird.  
  
     Der Name der Friend-Assembly, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird, darf nicht der starke Name von Assembly *B* sein: Er darf nicht die Assemblyversion, Kultur, Architektur oder das Token des öffentlichen Schlüssels enthalten.  
  
-   Wenn Assembly *A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von nicht signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Wenn Assembly *B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für Assembly *B* über die Projekteinstellung oder bei Verwendung der Befehlszeile die Compileroption `/keyfile` angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.  
  
-   Wenn es Hunderte von Typen in Assembly *A* gibt, die Sie für Assembly *B* freigeben möchten, müssen Sie allen <xref:System.Security.Permissions.StrongNameIdentityPermission> hinzufügen. Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.  
  
-   Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden. Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen als `internal` deklariert.  
  
 Informationen darüber, wie Sie auf `internal`-Typen und -Methoden einer Assembly aus einer Moduldatei (eine Datei mit der Erweiterung .netmodule) zugreifen können, finden Sie unter [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [Vorgehensweise: Erstellen von signierten Friend-Assemblys (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)

