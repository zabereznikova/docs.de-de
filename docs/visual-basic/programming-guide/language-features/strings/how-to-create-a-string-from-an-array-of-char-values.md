---
title: "How to: Create a String from An Array of Char Values (Visual Basic) | Microsoft Docs"
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
  - "examples [Visual Basic], arrays"
  - "examples [Visual Basic], Char data type"
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# How to: Create a String from An Array of Char Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Dieses Beispiel erstellt die Zeichenfolge "abcd" anhand von einzelnen Zeichen.  
  
## Beispiel  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## Kompilieren des Codes  
 Für diese Methode gelten keine besonderen Voraussetzungen.  
  
 Mit der Syntax `"a"c`, bei der ein einzelnes `c` auf ein Zeichen in Anführungszeichen folgt, wird ein Zeichenliteral erstellt.  
  
## Robuste Programmierung  
 Wenn die Zeichenfolge NULL\-Zeichen \(entspricht `Chr(0)`\) enthält, kann es bei der Verwendung der Zeichenfolge zu unerwarteten Ergebnissen kommen.  Das NULL\-Zeichen wird zwar der Zeichenfolge hinzugefügt; in bestimmten Situationen werden allerdings die darauf folgenden Zeichen nicht angezeigt.  
  
## Siehe auch  
 <xref:System.String>   
 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)