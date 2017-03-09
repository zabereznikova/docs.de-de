---
title: "Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36532"
  - "bc36532"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36532"
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Lambda\-Ausdruck wurde einem Delegaten zugewiesen, der über eine nicht kompatible Signatur verfügt.  Im folgenden Code verfügt der `Del`\-Delegat beispielsweise über zwei ganzzahlige Parameter.  
  
```vb#  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Der Fehler wird ausgelöst, wenn ein Lambda\-Ausdruck mit einem Argument als Typ `Del` deklariert wird:  
  
```vb#  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Fehler\-ID:** BC36532  
  
### So beheben Sie diesen Fehler  
  
-   Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda\-Ausdruck an, damit die Signaturen kompatibel sind.  
  
## Siehe auch  
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)