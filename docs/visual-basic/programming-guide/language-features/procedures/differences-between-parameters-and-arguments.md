---
title: "Differences Between Parameters and Arguments (Visual Basic) | Microsoft Docs"
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
  - "procedures, arguments"
  - "procedures, parameters"
  - "parameters, and arguments"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], and parameters"
  - "procedure parameters"
  - "parameters, definition"
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Differences Between Parameters and Arguments (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In den meisten Fällen benötigen Prozeduren einige Informationen zu den Umständen, unter denen sie aufgerufen wurden.  Prozeduren, die sich wiederholende und freigegebene Aufgaben ausführen, verwenden für jeden Aufruf andere Informationen.  Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücken, die beim Aufruf an die Prozedur übergeben werden.  
  
 Damit diese Informationen der Prozedur mitgeteilt werden, definiert die Prozedur einen *Parameter*, und der Aufrufcode übergibt an diesen Parameter ein *Argument*.  Stellen Sie sich vor, der Parameter sei eine Parklücke und das Argument ein Auto.  Ebenso wie verschiedene Autos zu unterschiedlichen Zeiten in einer Parklücke parken können, kann der Aufrufcode bei jedem Aufruf der Prozedur ein anderes Argument an den gleichen Parameter übergeben.  
  
## Parameter  
 Ein *Parameter* stellt einen Wert dar, der an die Prozedur übergeben werden muss, wenn Sie sie aufrufen.  Die Parameter der Prozedur werden in der Deklaration der Prozedur definiert.  
  
 Wenn Sie eine `Function`\-Prozedur oder eine `Sub`\-Prozedur definieren, geben Sie unmittelbar nach dem Prozedurnamen eine *Parameterliste* in Klammern an.  Für jeden Parameter geben Sie einen Namen, einen Datentyp und einen Übergabemechanismus \([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\) an.  Sie können auch angeben, dass ein Parameter optional ist.  Dies bedeutet, dass der aufrufende Code keinen Wert dafür übergeben muss.  
  
 Der Name jedes Parameters dient innerhalb der Prozedur als *lokale Variable*.  Sie verwenden den Parameternamen auf die gleiche Weise wie andere Variablen.  
  
## Argumente  
 Ein *Argument* stellt den Wert dar, den Sie an einen Prozedurparameter übergeben, wenn Sie die Prozedur aufrufen.  Der Aufrufcode stellt beim Aufrufen der Prozedur die Argumente zur Verfügung.  
  
 Wenn Sie eine `Function`\-Prozedur oder eine `Sub`\-Prozedur aufrufen, fügen Sie unmittelbar nach dem Prozedurnamen eine *Argumentliste* in runde Klammern ein.  Jedes Argument entspricht dem Parameter an der gleichen Position in der Liste.  
  
 Im Gegensatz zu Parametern haben Argumente keine Namen.  Jedes Argument ist ein Ausdruck, der 0 \(null\) oder mehr Variablen, Konstanten und Literale enthalten kann.  Der Datentyp des ausgewerteten Ausdrucks muss normalerweise mit dem Datentyp übereinstimmen, der für den entsprechenden Parameter definiert ist. In jedem Fall muss er in den Datentyp des Parameters konvertiert werden können.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Parameter for a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)