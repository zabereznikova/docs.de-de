---
title: "Call Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Call"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, Call statement"
  - "Call statement"
  - "procedures, calling"
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Call Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Überträgt die Steuerung an eine `Function`\-Prozedur, eine `Sub`\-Prozedur oder eine Prozedur in einer DLL \(Dynamic Link Library\).  
  
## Syntax  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## Teile  
 `procedureName`  
 Erforderlich.  Name der aufzurufenden Prozedur.  
  
 `argumentList`  
 Optional.  Variablen\- oder Ausdrucksliste mit den Argumenten, die beim Aufruf an die Prozedur übergeben werden.  Mehrere Argumente werden durch Komma voneinander getrennt.  Wenn Sie einen Wert für `argumentList` angeben, müssen Sie ihn in Klammern setzen.  
  
## Hinweise  
 Sie können das `Call`\-Schlüsselwort verwenden, wenn Sie eine Prozedur aufrufen.  Für die meisten Prozedur ist es nicht erforderlich, das Schlüsselwort zu verwenden.  
  
 Üblicherweise wird das Schlüsselwort `Call` aufgerufen, wenn der Ausdruck nicht mit einem Bezeichner beginnt.  Die Verwendung des Schlüsselworts für andere `Call` wird nicht empfohlen.  
  
 Wenn die Prozedur einen Wert zurückgibt, wird er von der `Call`\-Anweisung verworfen.  
  
## Beispiel  
 Der folgende Code zeigt zwei Beispielen gezeigt, wobei das `Call`\-Schlüsselwort ist erforderlich, um eine Prozedur aufrufen.  In beiden Beispielen wird der aufgerufene Ausdruck nicht mit einem Bezeichner.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## Siehe auch  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)