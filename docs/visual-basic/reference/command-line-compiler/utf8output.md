---
title: "/utf8output (Visual Basic) | Microsoft Docs"
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
  - "-utf8output compiler option [Visual Basic]"
  - "utf8output compiler option [Visual Basic]"
  - "/utf8output compiler option [Visual Basic]"
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /utf8output (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Zeigt die Compilerausgabe mit UTF\-8\-Codierung an.  
  
## Syntax  
  
```  
/utf8output[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  Die Standardeinstellung für diese Option ist `/utf8output-`. In diesem Fall erfolgt die Compilerausgabe nicht mit UTF\-8\-Codierung.  Das Festlegen von `/utf8output` entspricht dem Angeben von `/utf8output+`.  
  
## Hinweise  
 Bei einigen internationalen Konfigurationen kann die Compilerausgabe nicht ordnungsgemäß in der Konsole angezeigt werden.  Verwenden Sie bei diesen Konfigurationen `/utf8output`, und leiten Sie die Compilerausgabe in eine Datei um.  
  
> [!NOTE]
>  Die `/utf8output`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und die Compilerausgabe mit UTF\-8\-Codierung festgelegt.  
  
```  
vbc /utf8output in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)