---
title: "How to: Define Multiple Versions of a Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedures, overloading"
  - "procedures, multiple versions"
  - "procedure overloading, multiple versions"
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Define Multiple Versions of a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können durch *Überladen* mehrere Versionen einer Prozedur definieren. Es wird dann für jede Version der gleiche Name, jedoch eine andere Parameterliste verwendet.  Durch die Überladung können mehrere ähnliche Prozedurversionen definiert werden, ohne dass diese nach Namen voneinander unterschieden werden müssen.  
  
 Weitere Informationen hierzu finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
### So definieren Sie mehrere Versionen einer Prozedur  
  
1.  Schreiben Sie eine `Sub`\- oder `Function`\-Deklarationsanweisung für jede Version der Prozedur, die Sie definieren möchten.  Verwenden Sie in jeder Deklaration den gleichen Prozedurnamen.  
  
2.  Stellen Sie in jeder Deklaration das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)\-Schlüsselwort dem `Sub`\-Schlüsselwort bzw. dem `Function`\-Schlüsselwort voran.  Sie können das `Overloads`\-Schlüsselwort in den Deklarationen auch weglassen. Wenn Sie es aber in einer Deklaration angeben, müssen Sie es auch in allen anderen Deklarationen angeben.  
  
3.  Fügen Sie nach der Deklarationsanweisung den Prozedurcode für den speziellen Fall ein, in dem der Aufrufcode Argumente für die Parameterliste der betreffenden Version angibt.  Sie müssen nicht überprüfen, welche Parameter der Aufrufcode angibt.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] übergibt die Steuerung an die passende Prozedurversion.  
  
4.  Beenden Sie jede Version der Prozedur je nach Bedarf mit einer `End Sub`\-Anweisung oder einer `End Function`\-Anweisung.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Sub`\-Prozedur definiert, die eine Transaktion übermittelt, die mit dem Kontostand eines Kunden verrechnet werden soll.  Hier werden mithilfe des `Overloads`\-Schlüsselworts zwei Versionen der Prozedur definiert; eine Version erwartet die Angabe des Namens des Kunden und die andere seine Kontonummer.  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-multiple-vers_1.vb)]  
  
 Der Aufrufcode kann die Kundenkennung entweder als `String` oder als `Integer`\-Wert abrufen und dann in beiden Fällen dieselbe Aufrufanweisung verwenden.  
  
 Informationen dazu, wie diese beiden Versionen der `post`\-Prozedur aufgerufen werden, finden Sie unter [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md).  
  
## Kompilieren des Codes  
 Stellen Sie sicher, dass jede der überladenen Versionen den gleichen Prozedurnamen, aber eine andere Parameterliste hat.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)