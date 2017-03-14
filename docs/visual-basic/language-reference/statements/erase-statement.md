---
title: "Erase Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Erase"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Erase keyword"
  - "Erase statement"
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Erase Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wird zur Freigabe von Arrayvariablen und des Speichers, der für ihre Elemente benötigt wird, verwendet.  
  
## Syntax  
  
```  
Erase arraylist  
```  
  
## Teile  
 `arraylist`  
 Erforderlich.  Liste der zu löschenden Arrayvariablen.  Mehrere Variablen werden durch Komma voneinander getrennt.  
  
## Hinweise  
 Die `Erase`\-Anweisung kann nur auf Prozedurebene verwendet werden.  Das bedeutet, Sie können Arrays zwar in einer Prozedur freigeben, jedoch nicht auf Klassen\- oder Modulebene.  
  
 Statt die `Erase`\-Anweisung zu verwenden, können Sie den einzelnen Arrayvariablen auch `Nothing` zuweisen.  
  
## Beispiel  
 Im folgenden Beispiel werden mit der `Erase`\-Anweisung zwei Arrays gelöscht, und der von ihnen belegte Speicherplatz wird freigegeben \(jeweils 1000 bzw. 100 Speicherelemente\).  Anschließend weist die `ReDim`\-Anweisung dem dreidimensionalen Array eine neue Arrayinstanz zu.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## Siehe auch  
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)