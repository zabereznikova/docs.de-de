---
title: "Throw Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Throw"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "structured exception handling, throw statements"
  - "try-catch exception handling, throw statements"
  - "throw statement, about throw statements"
  - "throwing exceptions, throw statement"
  - "exception handling, throw statement"
  - "On Error statement, throwing exceptions"
  - "throwing exceptions"
  - "exception handling, unstructured"
  - "throw statement"
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Throw Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Löst innerhalb einer Prozedur eine Ausnahme aus.  
  
## Syntax  
  
```  
Throw [ expression ]  
```  
  
## Bestandteil  
 `expression`  
 Liefert Informationen über die auszulösende Ausnahme.  In einer `Catch`\-Anweisung optional, sonst erforderlich.  
  
## Hinweise  
 Die `Throw`\-Anweisung löst eine Ausnahme aus, die Sie mit Code für die strukturierte Ausnahmebehandlung \(`Try`...`Catch`...`Finally`\) oder mit Code für die unstrukturierte Ausnahmebehandlung \(`On Error GoTo`\) behandeln können.  Mit der `Throw`\-Anweisung können Sie Fehler im Code abfangen, da Visual Basic die Aufrufliste nach oben verfolgt, bis der geeignete Ausnahmebehandlungscode gefunden wird.  
  
 Eine `Throw`\-Anweisung ohne Ausdruck kann nur in einer `Catch`\-Anweisung verwendet werden. In diesem Fall wird erneut die Ausnahme ausgelöst, die gegenwärtig von der `Catch`\-Anweisung behandelt wird.  
  
 Die `Throw`\-Anweisung setzt die Aufrufliste für die `expression`\-Ausnahme zurück.  Wenn `expression` nicht bereitgestellt wird, bleibt die Aufrufliste unverändert.  Sie können über die <xref:System.Exception.StackTrace%2A>\-Eigenschaft auf die Aufrufliste für die Ausnahme zugreifen.  
  
## Beispiel  
 Im folgenden Code wird mit der `Throw`\-Anweisung eine Ausnahme ausgelöst:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:** `Interaction`  
  
 **Assembly:** Visual Basic\-Laufzeitbibliothek \(in Microsoft.VisualBasic.dll\)  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)