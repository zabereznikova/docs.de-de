---
title: "Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33000"
  - "vbc33000"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33000"
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können nur einen Operator deklarieren, der überladen werden kann.  In der folgenden Tabelle werden die Operatoren aufgelistet, die Sie deklarieren können.  
  
|Typ|Operatoren|  
|---------|----------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binär|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung \(unär\)|`CType`|  
  
 Beachten Sie, dass der Operator `=` in der Liste binärer Operatoren der Vergleichsoperator und nicht der Zuweisungsoperator ist.  
  
 **Fehler\-ID:** BC33000  
  
### So beheben Sie diesen Fehler  
  
1.  Wählen Sie einen Operator aus der Gruppe überladbarer Operatoren aus.  
  
2.  Wenn Sie einen Operator überladen müssen, der nicht direkt überladen werden kann, erstellen Sie eine `Function`\-Prozedur, die die entsprechenden Parameter akzeptiert und den entsprechenden Wert zurückgibt.  
  
## Siehe auch  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)