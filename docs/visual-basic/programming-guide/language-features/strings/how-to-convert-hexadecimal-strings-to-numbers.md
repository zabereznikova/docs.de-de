---
title: "How to: Convert Hexadecimal Strings to Numbers (Visual Basic) | Microsoft Docs"
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
  - "numbers, hexadecimals"
  - "hexadecimals, decimals"
  - "examples [Visual Basic], string conversion"
  - "decimals, hexadecimals"
  - "string conversion, hexadecimal to numbers"
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Convert Hexadecimal Strings to Numbers (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Beispiel wird eine Hexadezimalzeichenfolge mit der <xref:System.Convert.ToInt32%2A>\-Methode in eine ganze Zahl konvertiert.  
  
### So konvertieren Sie eine Hexadezimalzeichenfolge in eine Zahl  
  
-   Verwenden Sie die <xref:System.Convert.ToInt32%2A>\-Methode, um die zur Basis 16 ausgedrückte Zahl in eine ganze Zahl zu konvertieren.  
  
     Das erste Argument der <xref:System.Convert.ToInt32%2A>\-Methode ist die zu konvertierende Zeichenfolge.  Das zweite Argument beschreibt, mit welcher Basis die Zahl ausgedrückt ist; bei hexadezimalen Zahlen ist der Basiswert 16.  
  
     [!code-vb[VbVbalrStrings#62](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:System.Convert.ToInt32%2A>