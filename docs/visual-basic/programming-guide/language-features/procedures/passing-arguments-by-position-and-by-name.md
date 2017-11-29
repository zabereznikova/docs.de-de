---
title: "Übergeben von Argumenten nach Position und Name (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Übergeben von Argumenten nach Position und Name (Visual Basic)
Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden – oder Sie übergeben *namentlich*, ohne Berücksichtigung der positionieren.  
  
 Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument gefolgt von einem Doppelpunkt und einem Gleichheitszeichen deklarierten des (`:=`), gefolgt vom Argumentwert. Sie können benannte Argumente in beliebiger Reihenfolge angeben.  
  
 Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 Wenn Sie diese Prozedur aufrufen, können Sie die Argumente, die anhand der Position, anhand des Namens oder mithilfe einer Kombination aus beiden angeben.  
  
## <a name="passing-arguments-by-position"></a>Übergeben von Argumenten nach Position  
 Sie können die Prozedur aufrufen `studentInfo` mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen durch ein Komma getrennt halten. Im folgenden Beispiel wird `studentInfo` ohne die `age` Argument:  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>Übergeben von Argumenten nach Namen  
 Sie können alternativ Aufrufen `studentInfo` mit den nach Namen übergebenen Argumenten auch durch ein Komma getrennt, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Mischen von Argumenten nach Position und Name  
 Sie können von Argumenten nach Position und Name in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, halten die Stelle von ausgelassenen `age` Argument, da `birth` wird anhand des Namens übergeben.  
  
 Wenn Sie Argumente, indem Sie eine Mischung von Position und Name, den Positionsargumenten angeben müssen alle zuerst aufgeführt werden. Nachdem Sie ein Argument nach Namen angeben, müssen die übrigen Argumente alle namentlich sein.  
  
## <a name="supplying-optional-arguments-by-name"></a>Angeben optionaler Argumente nach Namen  
 Übergeben von Argumenten anhand des Namens ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehrere optionale Argumente aufweist. Wenn Sie Argumente nach Namen angeben, müssen Sie keinen aufeinanderfolgende Kommas zu verwenden, um fehlende Argumente. Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a>Einschränkungen bei der Angabe von Argumenten anhand des Namens  
 Sie können keine Argumente nach Namen, um zu vermeiden, Eingeben der erforderlichen Argumente übergeben. Sie können nur die optionalen Argumente auslassen.  
  
 Ein Parameterarray kann nicht anhand des Namens übergeben werden. Dies ist daran, dass wenn Sie die Prozedur aufrufen, Sie eine unbegrenzte Anzahl von kommagetrennten Argumenten für das Parameterarray geben und der Compiler nicht mehr als ein Argument mit einem einzelnen Namen zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Parameterarrays](./parameter-arrays.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
