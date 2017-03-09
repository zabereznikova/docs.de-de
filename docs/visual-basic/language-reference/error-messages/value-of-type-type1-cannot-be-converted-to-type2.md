---
title: "Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31194"
  - "bc31194"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31194"
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Wert vom Typ 'Typ1' kann nicht in 'Typ2' konvertiert werden.Rufen Sie mit der Value\-Eigenschaft den Zeichenfolgenwert des ersten Elements von '\<übergeordnetesElement\>' ab.  
  
 Es wurde versucht, ein XML\-Literal implizit in einen bestimmten Typ umzuwandeln.  Das XML\-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.  
  
 **Fehler\-ID:** BC31194  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie die `Value`\-Eigenschaft des XML\-Literals, um auf dessen Wert als `String` zu verweisen.  Verwenden Sie die `CType`\-Funktion, die eine weitere Typkonvertierungsfunktion darstellt, oder die <xref:System.Convert>\-Klasse, um den Wert in den angegebenen Typ umzuwandeln.  
  
## Siehe auch  
 <xref:System.Convert>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)