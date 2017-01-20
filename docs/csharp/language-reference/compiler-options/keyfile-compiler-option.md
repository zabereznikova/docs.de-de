---
title: "/keyfile (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keyfile compiler option [C#]"
  - "-keyfile compiler option [C#]"
  - "keyfile compiler option [C#]"
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /keyfile (C# Compiler Options)
Gibt den Namen der Datei an, die den kryptografischen Schlüssel enthält.  
  
## Syntax  
  
```  
/keyfile:file  
```  
  
## Argumente  
  
|Begriff|Definition|  
|-------------|----------------|  
|`file`|Der Name der Datei, die den Schlüssel für einen starken Namen enthält.|  
  
## Hinweise  
 Bei Verwendung dieser Option fügt der Compiler den öffentlichen Schlüssel aus der angegebenen Datei in das Assemblymanifest ein. Die fertige Assembly wird dann mit dem privaten Schlüssel signiert.  Geben Sie in der Befehlszeile sn \-k `file` ein, um eine Schlüsseldatei zu generieren.  
  
 Wenn Sie mit **\/target:module** kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die beim Kompilieren einer Anwendung mit [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) erstellt wird.  
  
 Die Verschlüsselungsinformationen können auch mit [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) an den Compiler übergeben werden.  Verwenden Sie [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn die Assembly teilweise signiert werden soll.  
  
 Falls sowohl \/keyfile als auch \/keycontainer \(entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut\) in derselben Kompilierung angegeben werden, verwendet der Compiler zuerst den Schlüsselcontainer.  Wenn dies erfolgreich ist, wird die Assembly mit den Informationen aus dem Schlüsselcontainer signiert.  Findet der Compiler den Schlüsselcontainer nicht, verwendet er die Datei, die mit \/keyfile angegeben wird.  Ist dies erfolgreich, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden in den Schlüsselcontainer installiert \(ähnlich wie mit sn \-i\), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass eine Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) und [Verzögertes Signieren einer Assembly](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Signierung**.  
  
3.  Ändern Sie die Eigenschaft **Schlüsseldatei mit starkem Namen auswählen**.  
  
 Der programmgesteuerte Zugriff auf diese Compileroption erfolgt mithilfe von <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)