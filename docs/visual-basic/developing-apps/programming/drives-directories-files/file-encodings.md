---
title: "File Encodings (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "character encodings"
  - "files, encoding"
  - "Unicode, file encoding"
  - "file encoding"
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# File Encodings (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden.  Codierungen können sich in Bezug auf die Unterstützung einzelner sprachspezifischer Zeichen unterscheiden. Im Allgemeinen empfiehlt sich jedoch die Verwendung von Unicode.  
  
 Beim Lesen und Schreiben von Dateien können nicht übereinstimmende Dateicodierungen zu Ausnahmen oder falschen Ergebnissen führen.  
  
## Arten von Codierungen  
 Beim Arbeiten mit Dateien empfiehlt sich die Verwendung von Unicode.  Unicode ist ein weltweit gültiger Standard für Zeichencodierungen, bei dem mithilfe von 16\-Bit\-Codewerten alle weltweit in der modernen Computertechnik verwendeten Zeichen dargestellt werden können, einschließlich technischer Symbole und Sonderzeichen für Veröffentlichungen.  
  
 Frühere Zeichencodierungsstandards basierten auf herkömmlichen Zeichensätzen. So werden z. B. beim Windows\-ANSI\-Zeichensatz mithilfe von 8\-Bit\-Codewerten oder Kombinationen von 8\-Bit\-Werten die Zeichen dargestellt, die in einer bestimmten Sprache oder geografischen Region vorkommen.  
  
## Encoding\-Klasse  
 Die <xref:System.Text.Encoding>\-Klasse stellt eine Zeichencodierung dar.  In dieser Tabelle werden die verfügbaren Typen von Codierungen aufgeführt und beschrieben.  
  
|||  
|-|-|  
|Name|Beschreibung|  
|<xref:System.Text.ASCIIEncoding>|Stellt eine ASCII\-Zeichencodierung von Unicode\-Zeichen dar.|  
|<xref:System.Text.UnicodeEncoding>|Stellt eine UTF\-16\-Codierung von Unicode\-Zeichen dar.|  
|<xref:System.Text.UTF32Encoding>|Stellt eine UTF\-32\-Codierung von Unicode\-Zeichen dar.|  
|<xref:System.Text.UTF7Encoding>|Stellt eine UTF\-7\-Codierung von Unicode\-Zeichen dar.|  
|<xref:System.Text.UTF8Encoding>|Stellt eine UTF\-8\-Codierung von Unicode\-Zeichen dar.|  
  
## Siehe auch  
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)