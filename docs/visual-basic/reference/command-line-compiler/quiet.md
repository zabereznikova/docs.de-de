---
title: "/quiet | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/quiet"
  - "quiet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-quiet compiler option [Visual Basic]"
  - "/quiet compiler option [Visual Basic]"
  - "quiet compiler option [Visual Basic]"
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /quiet
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Verhindert, dass der Compiler Code zu syntaxbezogenen Fehlern und Warnungen anzeigt.  
  
## Syntax  
  
```  
/quiet  
```  
  
## Hinweise  
 Standardmäßig ist `/quiet` nicht aktiv.  Wenn der Compiler syntaxbezogene Fehler oder Warnungen meldet, gibt er auch die entsprechende Zeile aus dem Quellcode aus.  Bei Anwendungen, die die Compilerausgabe analysieren, ist es sinnvoll, wenn der Compiler nur den Diagnosetext ausgibt.  
  
 Im folgenden Beispiel gibt `Module1` einen Fehler aus, der bei der Kompilierung ohne `/quiet` Quellcode einschließt.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Ausgabe:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 Bei einer Kompilierung mit `/quiet` gibt der Compiler nur Folgendes aus:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  Die `/quiet`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert. Code für syntaxbezogene Compilerdiagnosen wird nicht angezeigt:  
  
```  
vbc /quiet t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)