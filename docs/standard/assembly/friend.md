---
title: Friend-Assemblys
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: bf1cb28a6e3096a42aae1c777f6d2d6f9cc16c49
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774328"
---
# <a name="friend-assemblies"></a>Friend-Assemblys

Eine *Friend-Assembly* ist eine Assembly, die auf die [Friend-](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) oder [internen](../../csharp/language-reference/keywords/internal.md) (C#) Typen und Member einer anderen Assembly zugreifen kann. Wenn Sie eine Assembly als Friend-Assembly identifizieren, müssen Sie Typen und Member nicht mehr als öffentlich markieren, damit andere Assemblys auf sie zugreifen können. Dies ist insbesondere in folgenden Szenarios nützlich:

- Wenn der Testcode bei Komponententests in einer separaten Assembly ausgeführt wird, aber Zugriff auf Member in der getesteten Assembly benötigt, die als `internal` in C# oder `Friend` in Visual Basic markiert sind.

- Wenn beim Entwickeln einer Klassenbibliothek die Ergänzungen der Bibliothek in separaten Assemblys enthalten sind, aber Zugriff auf Member in vorhandenen Assemblys erfordern, die als `internal` in C# oder `Friend` in Visual Basic markiert sind.

## <a name="remarks"></a>Anmerkungen

Sie können das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> verwenden, um eine oder mehrere Friend-Assemblys für eine angegebene Assembly zu identifizieren. Im folgenden Beispiel wird das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> in *Assembly A* verwendet, und *Assembly B* wird als Friend-Assembly angegeben. Dadurch erhält *Assembly B* Zugriff auf alle Typen und Member in *Assembly A*, die als `internal` (C#) oder `Friend` (Visual Basic) markiert sind.

> [!NOTE]
> Wenn Sie eine Assembly wie *Assembly B* kompilieren, die auf interne Typen oder Member einer anderen Assembly wie *Assembly A* zugreift, müssen Sie den Namen der Ausgabedatei ( *.exe* oder *.dll*) explizit mithilfe der Compileroption **-out** festlegen. Dies ist erforderlich, da der Compiler den Namen für die Assembly, die er erstellt, noch nicht generiert hat, wenn er Bindungen an externe Referenzen vornimmt. Weitere Informationen hierzu finden Sie unter [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) oder [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

Nur Assemblys, die Sie explizit als Friends angeben, können auf die Typen und Member `internal` (C#) oder `Friend` (Visual Basic) zugreifen. Wenn *Assembly B* beispielsweise ein Friend von *Assembly A* ist und *Assembly C* auf *Assembly B* verweist, verfügt *Assembly C* nicht über Zugriff auf die Typen `internal` (C#) oder `Friend` (Visual Basic) in *Assembly A*.

Der Compiler führt eine grundlegende Prüfung des Namens der Friend-Assembly durch, der an das Attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> übergeben wird. Wenn *Assembly A* die *Assembly B* als Friend-Assembly deklariert, lauten die Validierungsregeln wie folgt:

- Wenn *Assembly A* einen starken Namen hat, muss *Assembly B* auch einen starken Namen haben. Der Name der Friend-Assembly, der an das Attribut übergeben wird, muss aus dem Namen der Assembly und dem öffentlichen Schlüssel der Schlüsseldatei mit starkem Namen bestehen, der zum Signieren von *Assembly B* verwendet wird.

     Der Name der Friend-Assembly, der an das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribut übergeben wird, kann nicht der starke Name der *Assembly B* sein. Fügen Sie keine Assemblyversion, Kultur, Architektur und kein öffentliches Schlüsseltoken ein.

- Wenn *Assembly A* keinen starken Namen hat, sollte der Name der Friend-Assembly nur aus dem Assemblynamen bestehen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys](create-unsigned-friend.md).

- Wenn *Assembly B* einen starken Namen hat, müssen Sie die Schlüsseldatei mit starkem Namen für *Assembly B* über die Projekteinstellung oder über die Compileroption `/keyfile` in der Befehlszeile angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von signierten Friend-Assemblys](create-signed-friend.md).

 Die Klasse <xref:System.Security.Permissions.StrongNameIdentityPermission> bietet auch die Möglichkeit zur Freigabe von Typen mit folgenden Unterschieden:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> gilt für einen einzelnen Typ, während eine Friend-Assembly für die gesamte Assembly gilt.

- Wenn Hunderte Typen in *Assembly A* vorliegen, die Sie für *Assembly B* freigeben möchten, müssen Sie <xref:System.Security.Permissions.StrongNameIdentityPermission> zu allen Typen hinzufügen. Wenn Sie eine Friend-Assembly verwenden, müssen Sie die Friend-Beziehung nur einmal deklarieren.

- Bei Verwendung von <xref:System.Security.Permissions.StrongNameIdentityPermission> müssen die Typen, die Sie freigeben möchten, als öffentlich deklariert werden. Wenn Sie eine Friend-Assembly verwenden, werden die freigegebenen Typen in `internal` (C#) oder `Friend` (Visual Basic) deklariert.

Informationen darüber, wie Sie über eine Moduldatei (eine Datei mit der Dateierweiterung *.netmodule*) auf die Typen und Methoden `internal` (C#) oder `Friend` (Visual Basic) zugreifen, finden Sie unter [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) oder [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Vorgehensweise: Erstellen von unsignierten Friend-Assemblys](create-unsigned-friend.md)
- [Vorgehensweise: Erstellen von signierten Friend-Assemblys](create-signed-friend.md)
- [Assemblys in .NET](index.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
