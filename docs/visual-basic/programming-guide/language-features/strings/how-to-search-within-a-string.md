---
title: "How to: Search Within a String (Visual Basic) | Microsoft Docs"
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
  - "strings [Visual Basic], finding"
  - "strings [Visual Basic], searching"
  - "examples [Visual Basic], strings"
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Search Within a String (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Das nachfolgende Beispiel ruft die <xref:System.String.IndexOf%2A>\-Methode für ein <xref:System.String>\-Objekt auf, um den Index des ersten Auftretens einer Teilzeichenfolge wiederzugeben.  
  
## Beispiel  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-search-within-a-s_1.vb)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Eine `Imports`\-Anweisung, die den <xref:System>\-Namespace angibt.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Robuste Programmierung  
 Die <xref:System.String.IndexOf%2A>\-Methode gibt den Speicherort des ersten Zeichens des ersten Auftretens der Teilzeichenfolge an.  Der Index ist nullbasiert, d. h., der Index des ersten Zeichens der Zeichenfolge ist 0 \(null\).  
  
 Wenn <xref:System.String.IndexOf%2A> die Teilzeichenfolge nicht finden kann, wird der Wert \-1 zurückgegeben.  
  
 Die <xref:System.String.IndexOf%2A>\-Methode unterscheidet zwischen Groß\- und Kleinschreibung und verwendet die aktuelle Kultur.  
  
 Zur optimalen Fehlerbehandlung können Sie die Zeichenfolgensuche in den `Try`\-Block einer [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)\-Konstruktion einbetten.  
  
## Siehe auch  
 <xref:System.String.IndexOf%2A>   
 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Strings](../../../../visual-basic/programming-guide/language-features/strings/index.md)