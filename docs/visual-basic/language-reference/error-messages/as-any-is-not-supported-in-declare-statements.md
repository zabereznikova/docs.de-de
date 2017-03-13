---
title: "&#39;As Any&#39; is not supported in &#39;Declare&#39; statements | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30828"
  - "vbc30828"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30828"
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &#39;As Any&#39; is not supported in &#39;Declare&#39; statements
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der `Any`\-Datentyp wurde in Visual Basic 6.0 und früheren Versionen in `Declare`\-Anweisungen verwendet, um die Verwendung von Argumenten zu ermöglichen, die Daten eines beliebigen Typs enthalten konnten.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] unterstützt jedoch Überladen und löst so den `Any`\-Datentyp ab.  
  
 **Fehler\-ID:** BC30828  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie Parameter des jeweiligen Typs, den Sie verwenden möchten. Beispiel:  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Verwenden Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut, um `As Any` anzugeben, wenn von der aufgerufenen Prozedur `Void*` erwartet wird.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)