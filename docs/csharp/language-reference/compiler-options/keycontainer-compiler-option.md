---
title: "/keycontainer (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/keycontainer"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keycontainer compiler option [C#]"
  - "keycontainer compiler option [C#]"
  - "-keycontainer compiler option [C#]"
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /keycontainer (C# Compiler Options)
Gibt den Namen des Kryptografieschlüsselcontainers an.  
  
## Syntax  
  
```  
/keycontainer:string  
```  
  
## Argumente  
 `string`  
 Der Name des Schlüsselcontainers mit starkem Namen.  
  
## Hinweise  
 Wenn Sie die Option **\/keycontainer** verwenden, erstellt der Compiler eine gemeinsam zu verwendende Komponente, indem er dem Assemblymanifest einen öffentlichen Schlüssel aus dem angegebenen Container hinzufügt und die generierte Assembly mit dem privaten Schlüssel signiert.  Um eine Schlüsseldatei zu erstellen, geben Sie Sn \- k `file` an der Befehlszeile ein. Sn \- i installiert das Schlüsselpaar in einen Container.  
  
 Wenn Sie mit [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly aufgenommen, wenn das Modul mit [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) in eine Assembly kompiliert wird.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut \(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>\) im Quellcode für ein beliebiges MSIL\-Modul \(Microsoft Intermediate Language\) angeben.  
  
 Die Verschlüsselungsinformationen können auch mit [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) an den Compiler übergeben werden.  Verwenden Sie [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn Sie dem Assemblymanifest den öffentlichen Schlüssel hinzufügen, die Assembly aber erst nach Abschluss des Testens signieren möchten.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) und [Verzögertes Signieren einer Assembly](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Die Compileroption ist in der Visual Studio\-Entwicklungsumgebung nicht verfügbar.  
  
 Der programmgesteuerte Zugriff auf diese Compileroption erfolgt mithilfe von <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)