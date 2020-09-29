---
description: -moduleassemblyname (C#-Compileroption)
title: -moduleassemblyname (C#-Compileroption)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 9131db17d767c76fe6a57f5d5353474153e0c269
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194088"
---
# <a name="-moduleassemblyname-c-compiler-option"></a>-moduleassemblyname (C#-Compileroption)

Gibt eine Assembly an, auf deren nicht öffentliche Typen ein .NET-Modul zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumente  

 `assembly_name`  
 Der Name einer Assembly, auf deren nicht öffentliche Typen die NETMODULE-Datei zugreifen kann  
  
## <a name="remarks"></a>Bemerkungen  

 **-moduleassemblyname** sollte beim Erstellen einer NETMODULE-Datei und wenn die folgenden Bedingungen erfüllt sind verwendet werden:  
  
- Die NETMODULE-Datei benötigt Zugriff auf nicht öffentliche Typen in einer vorhandenen Assembly.  
  
- Sie kennen den Namen der Assembly, in die die NETMODULE-Datei integriert wird.  
  
- Die vorhandene Assembly hat der Assembly, in die die NETMODULE-Datei integriert wird, Friend-Assembly-Zugriff erteilt.  
  
 Weitere Informationen zum Erstellen einer NETMODULE-Datei finden Sie unter [-target:module (C#-Compileroptionen)](./target-module-compiler-option.md).  
  
 Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).  
  
 Diese Option steht nicht in der Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird eine Assembly mit einem privaten Typ erstellt, und die Friend-Assembly-erhält Zugriff auf eine Assembly namens „csman_an_assembly“.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class
{  
    public void Test()
    {
        Console.WriteLine("An_Internal_Class.Test called");
    }  
}  
```  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird eine NETMODULE-Datei erstellt, das auf einen nicht öffentlichen Typ in der Assembly „moduleassemblyname_1.dll“ zugreift. Da bekannt ist, dass die NETMODULE-Datei in eine Assembly namens „csman_an_assembly“ integriert wird, kann **-moduleassemblyname** angegeben werden. Dadurch wird es der NETMODULE-Datei ermöglicht, auf nicht öffentliche Typen in einer Assembly zuzugreifen, die Friend-Assembly-Zugriff auf „csman_an_assembly“ zulässt.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a>Beispiel  

 In diesem Codebeispiel wird die Assembly „csman_an_assembly“ erstellt, die auf die zuvor erstellte Assembly und eine NETMODULE-Datei verweisen.  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
**An_Internal_Class.Test** aufgerufen

## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
