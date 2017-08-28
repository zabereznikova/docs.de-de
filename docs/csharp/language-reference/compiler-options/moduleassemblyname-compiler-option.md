---
title: -moduleassemblyname (C#-Compileroption)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /moduleassemblyname
dev_langs:
- CSharp
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2522609aa41ad944b37a8882c1cc56cd5967b330
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="moduleassemblyname-c-compiler-option"></a>/moduleassemblyname (C#-Compileroption)
Gibt eine Assembly an, auf deren nicht öffentliche Typen ein .NET-Modul zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumente  
 `assembly_name`  
 Der Name einer Assembly, auf deren nicht öffentliche Typen die NETMODULE-Datei zugreifen kann  
  
## <a name="remarks"></a>Hinweise  
 **/moduleassemblyname** sollte beim Erstellen einer NETMODULE-Datei, und wenn die folgenden Bedingungen erfüllt sind, verwendet werden:  
  
-   Die NETMODULE-Datei benötigt Zugriff auf nicht öffentliche Typen in einer vorhandenen Assembly.  
  
-   Sie kennen den Namen der Assembly, in die die NETMODULE-Datei integriert wird.  
  
-   Die vorhandene Assembly hat der Assembly, in die die NETMODULE-Datei integriert wird, Friend-Assembly-Zugriff erteilt.  
  
 Weitere Informationen zum Erstellen einer NETMODULE-Datei finden Sie unter [/target:module (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Weitere Informationen finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
 Diese Option steht nicht in der Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Assembly mit einem privaten Typ erstellt, und die Friend-Assembly-erhält Zugriff auf eine Assembly namens „csman_an_assembly“.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
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
 In diesem Beispiel wird eine NETMODULE-Datei erstellt, das auf einen nicht öffentlichen Typ in der Assembly „moduleassemblyname_1.dll“ zugreift. Da wir wissen, dass die NETMODULE-Datei in eine Assembly namens „csman_an_assembly“ integriert wird, können wir **/moduleassemblyname** angeben. Dadurch wird der NETMODULE-Datei ermöglicht, auf nicht öffentliche Typen in einer Assembly zuzugreifen, die Friend-Assembly-Zugriff auf „csman_an_assembly“ gewährt hat.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
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
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 **An_Internal_Class.Test** aufgerufen   
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

