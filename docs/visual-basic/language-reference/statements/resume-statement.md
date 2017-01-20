---
title: "Resume Statement | Microsoft Docs"
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
  - "vb.Resume"
  - "vb.ResumeNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Next statement, Resume"
  - "Resume Next statement"
  - "execution, resuming"
  - "run-time errors, resuming after"
  - "Resume statement, syntax"
  - "errors [Visual Basic], resuming after"
  - "Error statement, and Resume statement"
  - "execution"
  - "Resume statement"
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Resume Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Setzt nach Abschluss einer Fehlerbehandlungsroutine die Ausführung fort.  
  
 Wir empfehlen, dass Sie die strukturierte Ausnahmebehandlung im Code verwenden, wann immer dies möglich ist, und nicht anhand der unstrukturierten Ausnahmebehandlung und der `On Error` und `Resume`\-Anweisungen.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Syntax  
  
```  
Resume [ Next | line ]  
```  
  
## Teile  
 `Resume`  
 Erforderlich.  Wenn der Fehler in der gleichen Prozedur auftrat wie der Fehlerhandler, wird die Ausführung bei der Anweisung fortgesetzt, die den Fehler verursachte.  Trat der Fehler in einer aufgerufenen Prozedur auf, wird die Ausführung bei der Anweisung fortgesetzt, die zuletzt aus derjenigen Prozedur einen Aufruf ausführte, in der die Fehlerbehandlungsroutine enthalten ist.  
  
 `Next`  
 Optional.  Wenn der Fehler in der gleichen Prozedur auftrat wie der Fehlerhandler, wird die Ausführung bei der Anweisung fortgesetzt, die unmittelbar auf die Anweisung folgt, die den Fehler verursachte.  Wenn der Fehler in einer aufgerufenen Prozedur auftrat, wird die Ausführung bei der Anweisung fortgesetzt, die unmittelbar auf die Anweisung folgt, welche zuletzt einen Aufruf aus derjenigen Prozedur ausführte, in der die Fehlerbehandlungsroutine enthalten ist \(oder der `On Error Resume Next`\-Anweisung\).  
  
 `line`  
 Optional.  Die Ausführung wird mit der Zeile fortgesetzt, die im erforderlichen `line`\-Argument angegeben wird.  Das `line`\-Argument ist eine Zeilenmarke oder Zeilennummer und muss sich in der gleichen Prozedur befinden wie der Fehlerhandler.  
  
## Hinweise  
  
> [!NOTE]
>  Es wird empfohlen, die strukturierte Ausnahmebehandlung im Code verwenden, wann immer dies möglich ist, und nicht anhand der unstrukturierten Ausnahmebehandlung und der `On Error` und `Resume`\-Anweisungen.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Wenn Sie eine `Resume`\-Anweisung an einer anderen Stelle als in einer Fehlerbehandlungsroutine verwenden, tritt ein Fehler auf.  
  
 Die `Resume`\-Anweisung kann in keiner Prozedur verwendet werden, die eine `Try...Catch...Finally`\-Anweisung enthält.  
  
## Beispiel  
 In diesem Beispiel wird mithilfe der `Resume`\-Anweisung die Fehlerbehandlung in einer Prozedur beendet und dann die Ausführung mit der Anweisung fortgesetzt, die den Fehler verursacht hat.  Um die Verwendung der `Resume`\-Anweisung zu veranschaulichen, wird Fehler Nummer 55 generiert.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic\-Laufzeitbibliothek \(in Microsoft.VisualBasic.dll\)  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)