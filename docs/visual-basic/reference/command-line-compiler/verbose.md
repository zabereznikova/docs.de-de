---
title: "/verbose | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "verbose compiler option [Visual Basic]"
  - "-verbose compiler option [Visual Basic]"
  - "/verbose compiler option [Visual Basic]"
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /verbose
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler Status\- und Fehlermeldungen mit ausführlichem Wortlaut ausgibt.  
  
## Syntax  
  
```  
/verbose[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  `/verbose` entspricht `/verbose+`. In beiden Fällen gibt der Compiler Meldungen mit ausführlichem Wortlaut aus.  Der Standardwert für diese Option ist `/verbose-`.  
  
## Hinweise  
 Die  `/verbose`\-Option zeigt die Gesamtzahl der vom Compiler ausgegebenen Fehler an, meldet, welche Assemblys von einem bestimmten Modul geladen werden, und zeigt die gegenwärtig kompilierten Dateien an.  
  
> [!NOTE]
>  Die `/verbose`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert. Der Compiler gibt Statusinformationen mit ausführlichem Wortlaut aus.  
  
```  
vbc /verbose in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)