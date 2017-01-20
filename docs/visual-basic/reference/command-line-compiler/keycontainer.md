---
title: "/keycontainer | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-keycontainer compiler option [Visual Basic]"
  - "keycontainer compiler option [Visual Basic]"
  - "/keycontainer compiler option [Visual Basic]"
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /keycontainer
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## Syntax  
  
```  
/keycontainer:container  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`container`|Erforderlich.  Containerdatei, die den Schlüssel enthält.  Schließen Sie den Dateinamen in Anführungszeichen \(""\) ein, wenn der Name ein Leerzeichen enthält.|  
  
## Hinweise  
 Der Compiler erstellt die freigebbare Komponente, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert.  Geben Sie `sn -k` `file` in der Befehlszeile ein, um eine Schlüsseldatei zu generieren.  Mit der `-i` \-Option wird das Schlüsselpaar in einem Container installiert.  Weitere Informationen finden Sie unter [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 Wenn Sie mit `/target:module` kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die beim Kompilieren einer Anwendung mit [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) erstellt wird.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut \(<xref:System.Reflection.AssemblyKeyNameAttribute>\) im Quellcode für ein beliebiges MSIL\-Modul \(Microsoft Intermediate Language\) angeben.  
  
 Die Verschlüsselungsinformationen können auch mit [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) an den Compiler übergeben werden.  Verwenden Sie [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Weitere Informationen über das Signieren einer Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
> [!NOTE]
>  Die Option `/keycontainer` ist nicht innerhalb der Entwicklungsumgebung von Visual Studio verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird die Quelldatei `Input.vb` kompiliert und ein Schlüsselcontainer angegeben.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## Siehe auch  
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)