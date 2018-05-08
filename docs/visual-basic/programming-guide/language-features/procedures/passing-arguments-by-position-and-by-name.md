---
title: Übergeben von Argumenten nach Position und Name (Visual Basic)
ms.date: 02/01/2018
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49e313b2d5aa8302ea4b99e643e09f7b43659785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Übergeben von Argumenten nach Position und Name (Visual Basic)
Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden – oder Sie übergeben *namentlich*, ohne Berücksichtigung der positionieren.  
  
 Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument gefolgt von einem Doppelpunkt und einem Gleichheitszeichen deklarierten des (`:=`), gefolgt vom Argumentwert. Sie können benannte Argumente in beliebiger Reihenfolge angeben.  
  
 Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 Wenn Sie diese Prozedur aufrufen, können Sie die Argumente, die anhand der Position, anhand des Namens oder mithilfe einer Kombination aus beiden angeben.  
  
## <a name="passing-arguments-by-position"></a>Übergeben von Argumenten nach Position  
 Sie erreichen die `Display` Methode mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen durch ein Komma getrennt halten. Im folgenden Beispiel wird die `Display` Methode ohne die `age` Argument:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Übergeben von Argumenten nach Namen  
 Sie können alternativ Aufrufen `Display` mit den nach Namen übergebenen Argumenten auch durch ein Komma getrennt, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Übergeben von Argumenten nach dem Namen auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehrere optionale Argumente aufweist. Wenn Sie Argumente nach Namen angeben, müssen Sie keinen aufeinanderfolgende Kommas zu verwenden, um fehlende Argumente. Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Mischen von Argumenten nach Position und Name  

Sie können von Argumenten nach Position und Name in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, halten die Stelle von ausgelassenen `age` Argument, da `birth` wird anhand des Namens übergeben.  
  
In Versionen von Visual Basic vor 15.5 Wenn Sie Argumente, indem Sie eine Mischung von Position und Name, den Positionsargumenten angeben müssen alle zuerst aufgeführt werden. Nachdem Sie ein Argument nach Namen angeben, müssen alle übrigen Argumente alle anhand des Namens übergeben werden.  Beispielsweise beim folgenden Aufruf der `Display` Methode zeigt Compilerfehler [BC30241: benanntes Argument erwartet](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

Beginnend mit Visual Basic 15.5, können Positionsargumente Namensargumente folgen, wenn die Endwert Positionsargumenten in der richtigen Position befinden. Wenn unter Visual Basic 15.5, dem letzten Aufruf von kompiliert die `Display` Methode wird erfolgreich kompiliert, und generiert mehr Compilerfehler [BC30241](../../../misc/bc30241.md).  

Diese Fähigkeit zum Mischen und Zuordnen von benannten und Positionsparametern Argumente in beliebiger Reihenfolge ist besonders nützlich, wenn Sie ein benanntes Argument zu verwenden, um den Code verständlicher zu gestalten möchten. Beispielsweise die folgenden `Person` Klassenkonstruktor erfordert zwei Argumente des Typs `Person`, beide möglich `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

Mit gemischten benannten und Positionsparametern Argumenten können Sie den Zweck des Codes, deaktivieren, wenn der Wert von der `father` und `mother` Argumente ist `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Um Positionsargumente mit benannten Argumenten folgen zu können, müssen Sie Visual Basic-Projekt das folgende Element hinzufügen (\*.vbproj) Datei:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

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
