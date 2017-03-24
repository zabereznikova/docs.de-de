---
title: "Expression is a value and therefore cannot be the target of an assignment | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30068"
  - "vbc30068"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30068"
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Expression is a value and therefore cannot be the target of an assignment
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Anweisung versucht, einem Ausdruck einen Wert zuzuweisen.  Sie können einen Wert zur Laufzeit nur einer schreibbaren Variablen, einer Eigenschaft oder einem Arrayelement zuweisen.  Das folgende Beispiel zeigt, wie es zu diesem Fehler kommen kann.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Dieses Beispiel ist auch auf Eigenschaften und Arrayelemente übertragbar.  
  
 **Indirekter Zugriff.** Dieser Fehler kann auch durch indirekten Zugriff über einen Werttyp ausgelöst werden.  Im folgenden Codebeispiel wird versucht, den Wert von <xref:System.Drawing.Point> durch indirekten Zugriff über <xref:System.Windows.Forms.Control.Location%2A> festzulegen.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 Die letzte Anweisung im obigen Beispiel schlägt fehl, weil sie nur eine temporäre Zuordnung für die von der <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft zurückgegebene <xref:System.Drawing.Point>\-Struktur erstellt.  Eine Struktur ist ein Werttyp, und die temporäre Struktur bleibt nach der Ausführung der Anweisung nicht bestehen.  Das Problem lässt sich durch Deklarieren und Verwenden einer Variablen für <xref:System.Windows.Forms.Control.Location%2A> lösen. Durch diese Variable wird eine permanente Zuordnung für die <xref:System.Drawing.Point>\-Struktur erstellt.  Das folgende Beispiel zeigt Code, der die letzte Anweisung im obigen Beispiel ersetzen kann.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Fehler\-ID:** BC30068  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Anweisung einem Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne schreibbare Variable, eine Eigenschaft oder durch ein Arrayelement.  
  
-   Wenn die Anweisung indirekt über einen Werttyp \(in der Regel eine Struktur\) zugreift, erstellen Sie eine Variable, in welcher der Werttyp abgelegt werden kann.  
  
-   Weisen Sie der Variablen die entsprechende Struktur \(oder einen anderen Werttyp\) zu.  
  
-   Verwenden Sie die Variable für den Zugriff auf die Eigenschaft, sodass Sie dieser einen Wert zuweisen können.  
  
## Siehe auch  
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)