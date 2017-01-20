---
title: "REM Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.'"
  - "vb.Rem"
  - "Rem"
  - "'"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "REM statement"
  - "comments, Visual Basic code"
  - "code comments, Visual Basic"
  - "Visual Basic code, comments"
  - "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# REM Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wird verwendet, um erläuternde Anmerkungen zum Quellcode eines Programms hinzuzufügen.  
  
## Syntax  
  
```  
REM comment  
' comment  
```  
  
## Teile  
 `comment`  
 Optional.  Der Text eines beliebigen Kommentars, der eingefügt werden soll.  Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.  
  
## Hinweise  
 Eine `REM`\-Anweisung kann allein in einer Zeile stehen, sie kann jedoch auch zusammen mit einer anderen Anweisung in einer Zeile angegeben werden.  Die `REM`\-Anweisung muss die letzte Anweisung der Zeile sein.  Wenn `REM` auf eine andere Anweisung folgt, muss sie durch ein Leerzeichen von dieser Anweisung getrennt werden.  
  
 Anstelle von `REM` können Sie ein einfaches Anführungszeichen \(`'`\) verwenden.  Dies gilt, egal, ob der Kommentar in einer Zeile auf eine andere Anweisung folgt oder alleine in einer Zeile steht.  
  
> [!NOTE]
>  Sie können eine `REM`\-Anweisung nicht durch Verwendung einer Zeilenfortsetzungszeichenfolge \(`_`\) fortsetzen.  Der Compiler untersucht die Zeichen nach dem Beginn eines Kommentars nicht auf besondere Bedeutungen.  Bei einem mehrzeiligen Kommentar müssen Sie in jeder Zeile eine weitere `REM`\-Anweisung oder das Kommentarsymbol \(`'`\) eingeben.  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der `REM`\-Anweisung veranschaulicht, die für erläuternde Hinweise im Programm verwendet wird.  Es zeigt darüber hinaus, wie das einfache Anführungszeichen \(`'`\) anstelle von `REM` verwendet werden kann.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## Siehe auch  
 [Comments in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)