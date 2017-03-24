---
title: "/moduleassemblyname (C# Compiler Option) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/moduleassemblyname"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "moduleassemblyname compiler option [C#]"
  - "/moduleassemblyname compiler option [C#]"
  - ".moduleassemblyname compiler option [C#]"
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# /moduleassemblyname (C# Compiler Option)
Gibt eine Assembly an, auf deren nicht öffentliche Typen ein netmodule zugreifen kann.  
  
## Syntax  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Argumente  
 `assembly_name`  
 Der Name der Assembly, auf die nicht öffentliche Typen .netmodule zugreifen kann.  
  
## Hinweise  
 **\/moduleassemblyname** sollte verwendet werden, wenn .netmodule erstellt wird und wenn die folgenden Bedingungen erfüllt sind:  
  
-   Der .netmodule\-Anforderungszugriff an nicht öffentlichen Typen in eine vorhandene Assembly ein.  
  
-   Sie kennen den Namen der Assembly, in die .netmodule erstellt wird.  
  
-   Die vorhandene Assembly verfügt friend\-Assemblyzugriff der Assembly gewährt, in die .netmodule erstellt wird.  
  
 Weitere Informationen zum Erstellen von .netmodule, finden Sie unter [\/target:module \(Create Module to Add to Assembly\)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Weitere Informationen zu friend\-Assemblys finden Sie unter [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Diese Option ist nicht innerhalb der Entwicklungsumgebung, sondern nur bei der Kompilierung über die Befehlszeile verfügbar.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
## Beispiel  
 In diesem Beispiel wird eine Assembly mit einem privaten Typ erstellt, die einer Assembly mit dem Namen csman\_an\_assembly friend\-Assemblyzugriff gewährt.  
  
```  
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
  
## Beispiel  
 Dieses Beispiel erstellt .netmodule, das auf ein nicht öffentlicher Typ in der Assembly moduleassemblyname\_1.dll zugreift.  Durch das Wissen, dass dieses .netmodule in eine Assembly erstellt wird, wird compilergenerierter csman\_an\_assembly, wir kann **\/moduleassemblyname** angeben auf und erlaubte .netmodule an nicht öffentlichen Zugriff, Typen in einer Assembly, die zu csman\_an\_assembly friend\-Assemblyzugriff erteilt hat.  
  
```  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## Beispiel  
 Dieses Codebeispiel erstellt die Assembly csman\_an\_assembly und verweist auf die Assembly und zuvor\-erstellte .netmodule.  
  
```  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
  **An\_Internal\_Class.Test wurde aufgerufen**   
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)