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
ms.openlocfilehash: bdaa0351e288b85a3e35818c0f53ef4d772932e5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183866"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Übergeben von Argumenten nach Position und Name (Visual Basic)
Beim Aufruf einer `Sub` oder `Function` Verfahren können Sie Argumente übergeben *anhand der Position* – in der Reihenfolge, in dem sie in der Definition der Prozedur angezeigt werden, oder Sie übergeben diese *anhand des Namens*, ohne Bezug zum Positionieren.  
  
 Wenn Sie ein Argument nach Namen übergeben, geben Sie das Argument deklarierten Namen, die von einem Doppelpunkt und einem Gleichheitszeichen gefolgt des (`:=`), gefolgt von den Wert des Arguments. Sie können die benannten Argumente in beliebiger Reihenfolge angeben.  
  
 Beispielsweise die folgenden `Sub` Prozedur akzeptiert drei Argumente:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 Wenn Sie diese Prozedur aufrufen, können Sie die Argumente nach Position, anhand des Namens oder mithilfe einer Kombination dieser beiden angeben.  
  
## <a name="passing-arguments-by-position"></a>Übergeben von Argumenten nach Position  
 Rufen Sie die `Display` Methode mit den Argumenten nach Position übergebenen und durch Kommas voneinander getrennt, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Wenn Sie ein optionales Argument in einer Argumentliste mit Feldern fester Breite auslassen, müssen Sie stattdessen mit einem Komma halten. Im folgenden Beispiel wird die `Display` -Methode ohne die `age` Argument:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Übergeben von Argumenten nach Namen  
 Sie können alternativ Aufrufen `Display` mit den Argumenten, die anhand des Namens übergeben wird, auch durch Kommas getrennt, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Übergeben von Argumenten anhand des Namens auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehr als ein optionales Argument. Wenn Sie Argumente nach Namen angeben, müssen Sie nicht aufeinander folgende Kommas zu verwenden, um fehlende Argumente. Übergeben von Argumenten nach Namen erleichtert auch zum Nachverfolgen der Argumente übergeben und welche weggelassen werden.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Mischen von Argumenten nach Position und Name  

Sie können Argumente nach Position und Name in einem einzelnen Prozeduraufruf, bereitstellen, wie im folgenden Beispiel gezeigt:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 Im vorherigen Beispiel kein zusätzliches Komma ist erforderlich, um die Stelle der ausgelassenen aufzunehmen `age` -Argument, da `birth` wird anhand des Namens übergeben.  
  
In Versionen vor Version 15.5 von Visual Basic Wenn Sie Argumente, indem eine Mischung von Position und Name, die positionellen Argumente angeben müssen alle zuerst aufgeführt werden. Nachdem Sie ein Argument nach Namen angeben, müssen alle übrigen Argumente alle anhand des Namens übergeben werden.  Beispielsweise der folgende Aufruf von der `Display` Methode zeigt Compilerfehler [BC30241: benanntes Argument erwartet](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

Ab Visual Basic 15.5 können positionelle Argumente benannte Argumente folgen, wenn die abschließende positionellen Argumente in der richtigen Position befinden. Wenn Sie mit dem vorherigen Aufruf von Visual Basic 15.5 kompiliert die `Display` Methode wird erfolgreich kompiliert, und nicht mehr generiert den Compilerfehler [BC30241](../../../misc/bc30241.md).  

Diese Fähigkeit zum Mischen und Zuordnen von benannten und Positionsparametern Argumente in beliebiger Reihenfolge ist besonders nützlich, wenn Sie ein benanntes Argument zu verwenden, um Ihren Code besser lesbar zu machen möchten. Beispielsweise die folgenden `Person` Klassenkonstruktor erfordert zwei Argumente des Typs `Person`, beide möglich `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

Mit gemischten benannten und Positionsparametern Argumenten können Sie die Absicht des Codes, zu löschen, wenn der Wert des der `father` und `mother` Argumente sind `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Um positionelle Argumente mit benannten Argumenten folgen zu können, müssen Sie Visual Basic-Projekt das folgende Element hinzufügen (\*.vbproj) Datei:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Einschränkungen bei der Angabe von Argumenten, die anhand des Namens  

Argumente können nicht anhand des Namens nicht eingeben müssen die erforderlichen Argumente übergeben werden. Sie können nur optionale Argumente auslassen.  
  
Sie können nicht anhand des Namens ein Parameterarray übergeben. Dies ist daran, dass wenn Sie die Prozedur aufrufen, eine unbestimmte Anzahl von kommagetrennten Argumenten für das Parameterarray bereitgestellt, und der Compiler kann nicht mehr als ein Argument mit einem einzigen Namen zuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Parameterarrays](./parameter-arrays.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
