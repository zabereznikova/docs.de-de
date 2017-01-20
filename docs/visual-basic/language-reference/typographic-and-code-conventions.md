---
title: "Typographic and Code Conventions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "coding conventions, Visual Basic"
  - "best practices, coding conventions"
  - "conventions, Visual Basic coding"
  - "typographic conventions"
  - "document conventions"
  - "conventions, documentation"
  - "Visual Basic code, conventions"
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Typographic and Code Conventions (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

In der Dokumentation zu Visual Basic werden folgende Code\- und typografische Konventionen verwendet.  
  
## Typografische Konventionen  
  
|Beispiel|Beschreibung|  
|--------------|------------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Sprachspezifische Schlüsselwörter und Laufzeit\-Member beginnen mit einem Großbuchstaben und werden wie in diesem Beispiel formatiert.|  
|KleinesProjekt, SchaltflächenAuflistung|Wörter und Begriffe, zu deren Eingabe Sie aufgefordert werden, werden wie in diesem Beispiel formatiert.|  
|[Module Statement](../../visual-basic/language-reference/statements/module-statement.md)|Links, auf die Sie klicken können, um auf eine andere Hilfeseite zu gelangen, werden wie in diesem Beispiel formatiert.|  
|*object*, *variableName*, `argumentList`|Platzhalter für von Ihnen angegebene Informationen werden wie in diesem Beispiel formatiert.|  
|\[ Shadows \], \[ *expressionList* \]|In der Syntax werden optionale Elemente in Klammern eingeschlossen.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Wenn zwischen zwei oder mehr Elementen auszuwählen ist, werden die Elemente in Syntaxangaben in geschweifte Klammern eingeschlossen und durch senkrechte Striche getrennt.<br /><br /> Es ist genau ein Element auszuwählen.|  
|\[ `Protected` &#124; `Friend` \]|Wenn aus zwei oder mehr Elementen ausgewählt werden kann, werden die Elemente in Syntaxangaben in eckige Klammern eingeschlossen und durch senkrechte Striche getrennt.<br /><br /> Sie können eine beliebige Kombination der Elemente oder kein Element auswählen.|  
|\[{ `ByVal` &#124; `ByRef` }\]|Wenn maximal ein Element ausgewählt werden kann, jedoch kein Element ausgewählt werden muss, werden die Elemente in Syntaxangaben in eckige und geschweifte Klammern eingeschlossen und durch senkrechte Striche getrennt.|  
|*Membername* 1, *Membername*2, *Membername*3|Mehrere Instanzen des gleichen Platzhalters werden, wie im Beispiel gezeigt, durch Subskripte unterschieden.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|Auslassungspunkte \(…\) werden in Syntaxangaben verwendet, um eine unbestimmte Anzahl von Elementen des Elementtyps zu bezeichnen, der unmittelbar vor den Auslassungspunkten steht.<br /><br /> Im Code bedeutet eine Ellipse hingegen, dass aus Gründen der Übersichtlichkeit Code ausgelassen wurde.|  
|ESC, EINGABETASTE|Tastennamen und Tastenkombinationen auf der Tastatur werden in Großbuchstaben angezeigt.|  
|ALT\+F1|Steht zwischen Tastennamen ein Pluszeichen \(\+\), müssen Sie die eine Taste gedrückt halten, während Sie die andere drücken.  So bedeutet z. B. ALT\+F1, dass Sie die ALT\-TASTE gedrückt halten müssen, während Sie die F1\-TASTE drücken.|  
  
## Codekonventionen  
  
|Beispiel|Beschreibung|  
|--------------|------------------|  
|`sampleString = "Hello, world!"`|Codebeispiele werden in einer Schriftart mit fester Zeichenbreite angezeigt und werden wie in diesem Beispiel formatiert.|  
|Die vorherige Anweisung setzt den Wert von `sampleString` auf "Hello, world\!".|In erläuterndem Text werden Codeelemente in einer Schriftart mit fester Zeichenbreite angezeigt, wie in diesem Beispiel gezeigt.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Codekommentare werden durch ein Apostroph \('\) oder das Schlüsselwort REM eingeleitet.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Ein Leerzeichen mit anschließendem Unterstrich \( \_\) am Zeilenende gibt an, dass die Anweisung in der nächsten Zeile fortgesetzt wird.|  
  
## Siehe auch  
 [Visual Basic Language Reference](../../visual-basic/language-reference/index.md)   
 [Stichwörter](../../visual-basic/language-reference/keywords/index.md)   
 [Visual Basic Runtime Library Members](../../visual-basic/language-reference/runtime-library-members.md)   
 [Visual Basic Naming Conventions](../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Comments in Code](../../visual-basic/programming-guide/program-structure/comments-in-code.md)