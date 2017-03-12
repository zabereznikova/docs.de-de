---
title: "Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc31393"
  - "vbc31393"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31393"
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Ausdruck wird als Typ ausgewertet, den die Common Language Runtime \(CLR\) nicht mit Boxing konvertieren kann, der jedoch Boxing erfordert.  
  
 Als *Boxing* wird die Verarbeitung bezeichnet, die zum Konvertieren eines Typs in `Object` oder ggf. in <xref:System.ValueType> erforderlich ist.  Die Common Language Runtime kann bestimmte Typen, z. B. <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle> und <xref:System.TypedReference>, nicht mit Boxing konvertieren.  
  
 Dieser Ausdruck versucht mithilfe des eingeschränkten Typs eine Methode aufzurufen, die von <xref:System.Object> oder <xref:System.ValueType> geerbt wird, z. B. <xref:System.Object.GetHashCode%2A> oder <xref:System.Object.ToString%2A>.  Um auf diese Methode zuzugreifen, hat [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] eine implizite Boxingkonvertierung versucht, die diesen Fehler verursacht.  
  
 **Fehler\-ID:** BC31393  
  
### So beheben Sie diesen Fehler  
  
1.  Suchen Sie den Ausdruck, der als der genannte Typ ausgewertet wird.  
  
2.  Suchen Sie den Teil der Anweisung, der versucht, die von <xref:System.Object> oder <xref:System.ValueType> geerbte Methode aufzurufen.  
  
3.  Ändern Sie die Anweisung, um den Methodenaufruf zu vermeiden.  
  
## Siehe auch  
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)