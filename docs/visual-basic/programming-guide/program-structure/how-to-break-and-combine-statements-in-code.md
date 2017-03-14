---
title: "Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb._"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Doppelpunkte (:)"
  - "Zeilenfortsetzung"
  - "_ (Zeilenfortsetzungszeichen)"
  - ": (Zeilenseparatorzeichen)"
  - "Visual Basic-Code, Zeilenumbrüche in"
  - "Visual Basic-Code, Zeilenumbrüche"
  - "Visual Basic-Code, Zeilenfortsetzung"
  - "Lange Codezeilen"
  - "Zeilenabschluss"
  - "Zeilenfortsetzungszeichenfolge"
  - "Unterstriche, In Code"
  - "Anweisungen [Visual Basic], Zeilenfortsetzung in"
  - "Zeilenumbrüche, In Code"
  - "Zeilenfortsetzungszeichen"
  - "Visual Basic-Code, Zeilenfortsetzung in"
  - "Anweisungen [Visual Basic], Zeilenumbrüche in"
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Beim Schreiben von Code kommt es hin und wieder vor, dass Sie umfangreiche Anweisungen erstellen, die im Code\-Editor einen horizontalen Bildlauf erfordern.  Obwohl dies nicht die \- Methode auswirkt, wird der Code ausgeführt, können sie schwierig, damit Sie oder eine andere Person den Code liest, während er auf dem Bildschirm.  In diesem Fall empfiehlt es sich, die lange Anweisung auf mehrere Zeilen zu umbrechen.  
  
### So umbrechen Sie eine einzige Anweisung auf mehrere Zeilen  
  
-   Verwenden Sie an der Stelle, an der die Zeile umbrochen werden soll, das Zeilenfortsetzungszeichen. Dieses ist ein Unterstrich \(`_`\).  Der Unterstrich muss ein Leerzeichen unmittelbar vorangestellt werden und ein Zeilenabschlusszeichen \(Wagenrücklauf\) und werden.  
  
    > [!NOTE]
    >  In einigen Fällen wenn Sie das Zeilenfortsetzungszeichen weglassen, wird der Visual Basic\-Compiler implizit die \- Anweisung in der nächsten Codezeile fortgesetzt.  Eine Liste von Syntaxelementen, für die Sie das Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Im folgenden Beispiel wird die Anweisung in vier Zeilen aufgegliedert, wobei alle Zeilen bis auf die letzte mit Zeilenfortsetzungszeichen enden:  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Code ist durch die Verwendung dieser Zeichenfolge besser lesbar, sowohl online als auch in gedruckter Fassung.  
  
     Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein.  Sie können Kein einige in der gleichen Zeile folgen.  
  
     In Bezug, wo Sie das Zeilenfortsetzungszeichen verwenden kann, beispielsweise können Sie es nicht mitten in einem Argumentnamen verwenden.  Sie können eine Argumentliste durch ein Zeilenfortsetzungszeichen umbrechen, dabei müssen aber die einzelnen Argumentnamen intakt bleiben.  
  
     Sie können einen Kommentar nicht fortsetzen, indem Sie ein Zeilenfortsetzungszeichen verwenden.  Der Compiler überprüft die Zeichen in einem Kommentar besondere Bedeutungen.  Bei einem mehrzeiligen Kommentar müssen Sie das Kommentarsymbol \(`'`\) in jeder Zeile erneut eingeben.  
  
 Obwohl, jede Anweisung in einer eigenen Zeile platziert die empfohlene Methode ist, ermöglicht [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Sie in auch mehrere Anweisungen in der gleichen Zeile unterbringen.  
  
### So platzieren Sie mehrere Anweisungen in der gleichen Zeile  
  
-   Trennen Sie die Anweisungen mit einem Doppelpunkt \(`:`\). Beispiel:  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)