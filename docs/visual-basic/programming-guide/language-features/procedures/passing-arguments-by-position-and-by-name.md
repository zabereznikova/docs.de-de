---
title: "Passing Arguments by Position and by Name (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arguments [Visual Basic], passing by name"
  - "procedures, arguments"
  - ":= passing arguments"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "named arguments, passing arguments"
  - "arguments [Visual Basic], passing by position"
  - "Function procedures, passing arguments"
  - "named parameters, passing arguments"
  - "named arguments"
  - "passing parameters, named parameter arguments"
  - "passing parameters, by position"
  - "procedures, calling"
  - "named parameters"
  - "Sub procedures, passing arguments"
  - "argument passing"
  - "passing parameters, by name"
  - "argument passing, by position"
  - "arguments [Visual Basic], listing by name"
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Passing Arguments by Position and by Name (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine `Sub`\- oder `Function`\-Prozedur aufrufen, können Sie Argumente *durch die Position* übergeben, d. h. in der Reihenfolge, in der sie in der Prozedurdefinition aufgeführt werden, oder *durch Namen* unabhängig von der Position.  
  
 Bei der Übergabe eines Arguments durch Namen geben Sie den deklarierten Namen des Arguments, gefolgt von einem Doppelpunkt, einem Gleichheitszeichen \(`:=`\) und dem Argumentwert an.  Benannte Argumente können in beliebiger Reihenfolge angegeben werden.  
  
 Die `Sub`\-Prozedur im folgenden Beispiel übernimmt z. B. drei Argumente:  
  
 [!code-vb[VbVbcnProcedures#41](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-pos_1.vb)]  
  
 Bei Aufrufen dieser Prozedur können Sie die Argumente durch Position, durch Namen oder unter Verwendung beider Methoden bereitstellen.  
  
## Übergeben von Argumenten durch Position  
 Die `studentInfo` \-Prozedur kann, wie im folgenden Beispiel gezeigt, mit durch Position übergebenen, durch Kommas getrennten Argumenten aufgerufen werden:  
  
 [!code-vb[VbVbcnProcedures#42](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-pos_2.vb)]  
  
 Wenn Sie ein optionales Argument in einer positionellen Argumentliste auslassen, müssen Sie seinen Platz mit einem Komma freihalten.  Im folgenden Beispiel wird `studentInfo` ohne das `age` \-Argument aufgerufen:  
  
 [!code-vb[VbVbcnProcedures#43](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-pos_3.vb)]  
  
## Übergeben von Argumenten durch Namen  
 Die `studentInfo` \-Prozedur kann auch, wie im folgenden Beispiel gezeigt, mit durch Namen übergebenen, durch Kommas getrennten Argumenten aufgerufen werden:  
  
 [!code-vb[VbVbcnProcedures#44](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-pos_4.vb)]  
  
## Mischen von Argumenten durch Position und durch Namen  
 In ein und demselben Prozeduraufruf können Sie Argumente sowohl durch Position als auch durch Namen angeben, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#45](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-pos_5.vb)]  
  
 Im vorhergehenden Beispiel muss der Platz des ausgelassenen `age` \-Arguments nicht durch ein zusätzliches Komma freigehalten werden, da `birth` durch Namen übergeben wird.  
  
 Wenn Sie Argumente durch Position und durch Namen angeben, müssen alle positionellen Argumente zuerst aufgeführt werden.  Sobald Sie ein Argument durch Namen angeben, müssen auch alle darauf folgenden Argumente durch Namen übergeben werden.  
  
## Angeben optionaler Argumente durch Namen  
 Argumente durch Namen zu übergeben ist vor allem dann sinnvoll, wenn eine Prozedur mit mehr als einem optionalen Argument aufgerufen wird.  Bei der Angabe von Argumenten durch Namen müssen fehlende positionelle Argumente nicht durch aufeinander folgende Kommas gekennzeichnet werden.  Außerdem erleichtert die Argumentübergabe durch Namen den Überblick über die übergebenen und die weggelassenen Argumente.  
  
## Beschränkungen bei der Bereitstellung von Argumenten durch Namen  
 Auch bei der Argumentübergabe durch Namen müssen erforderliche Argumente eingegeben werden.  Weggelassen werden dürfen nur optionale Argumente.  
  
 Parameterarrays können nicht durch Namen übergeben werden,  da für Parameterarrays beim Aufrufen der Prozedur eine unbestimmte Anzahl von durch Trennzeichen getrennten Argumenten bereitgestellt wird und der Compiler einem Namen immer nur ein Argument zuordnen kann.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)