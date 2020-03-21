---
title: Übergeben von Argumenten nach Position und Name
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401436"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Übergeben von Argumenten nach Position und Name (Visual Basic)

Wenn Sie `Sub` eine `Function` oder eine Prozedur aufrufen, können Sie Argumente nach *Position* übergeben – in der Reihenfolge, in der sie in der Definition der Prozedur angezeigt werden – oder Sie können sie mit *Namen*übergeben, ohne Rücksicht auf die Position.

Wenn Sie ein Argument nach Namen übergeben, geben Sie den deklarierten Namen`:=`des Arguments an, gefolgt von einem Doppelpunkt und einem Gleichheitszeichen ( ), gefolgt vom Argumentwert. Sie können benannte Argumente in beliebiger Reihenfolge angeben.

Die folgende `Sub` Prozedur führt z. B. drei Argumente an:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Wenn Sie diese Prozedur aufrufen, können Sie die Argumente nach Position, Name oder mit einer Mischung aus beidem angeben.

## <a name="passing-arguments-by-position"></a>Übergeben von Argumenten nach Position

Sie können `Display` die Methode aufrufen, deren Argumente von position übergeben und durch Kommas getrennt werden, wie im folgenden Beispiel gezeigt:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Wenn Sie ein optionales Argument in einer Positionsargumentliste weglassen, müssen Sie seinen Platz mit einem Komma halten. Im folgenden Beispiel `Display` wird `age` die Methode ohne das Argument auf:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Übergeben von Argumenten nach Name

Alternativ können Sie `Display` mit den Argumenten aufrufen, die mit namenweise übergeben werden, auch durch Kommas getrennt, wie im folgenden Beispiel gezeigt:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Das Übergeben von Argumenten nach Namen auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur aufrufen, die mehr als ein optionales Argument enthält. Wenn Sie Argumente nach Namen angeben, müssen Sie keine aufeinander folgenden Kommas verwenden, um fehlende Positionsargumente zu bezeichnen. Das Übergeben von Argumenten nach Namen erleichtert es auch, nachzuverfolgen, welche Argumente Sie übergeben und welche Sie auslassen.

## <a name="mixing-arguments-by-position-and-by-name"></a>Mischen von Argumenten nach Position und Name

Sie können Argumente sowohl nach Position als auch nach Namen in einem einzelnen Prozeduraufruf angeben, wie im folgenden Beispiel gezeigt:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

Im vorherigen Beispiel ist kein zusätzliches Komma erforderlich, `age` um `birth` die Stelle des ausgelassenen Arguments zu halten, da es mit dem Namen übergeben wird.

Wenn Sie in Versionen von Visual Basic vor 15.5 Argumente durch eine Mischung aus Position und Name angeben, müssen alle Positionsargumente an erster Stelle stehen. Nachdem Sie ein Argument mit Namen geliefert haben, müssen alle verbleibenden Argumente mit namenweise übergeben werden.  Der folgende Aufruf der `Display` Methode zeigt beispielsweise den Compilerfehler [BC30241: Named argument expected](../../../misc/bc30241.md)an.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Ab Visual Basic 15.5 können Positionsargumente benannten Argumenten folgen, wenn sich die Endpositionsargumente an der richtigen Position befinden. Wenn unter Visual Basic 15.5 kompiliert, wird der vorherige Aufruf der `Display` Methode erfolgreich kompiliert und generiert nicht mehr den Compilerfehler [BC30241](../../../misc/bc30241.md).

Diese Möglichkeit, benannte und positionsgesteuerte Argumente in beliebiger Reihenfolge zu mischen und abzugleichen, ist besonders nützlich, wenn Sie ein benanntes Argument verwenden möchten, um den Code lesbarer zu machen. Der folgende `Person` Klassenkonstruktor erfordert z. `Person`B. zwei Argumente `Nothing`vom Typ , die beide sein können.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

Die Verwendung gemischter Named- und Positionsargumente hilft, die Absicht `father` `mother` des `Nothing`Codes klar zu machen, wenn der Wert der und-Argumente:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Um Positionsargumenten mit benannten Argumenten zu folgen, müssen\*Sie das folgende Element zu Ihrer Visual Basic-Projektdatei (.vbproj) hinzufügen:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie [unter Festlegen der Visual Basic-Sprachversion](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Einschränkungen bei der Bereitstellung von Argumenten nach Name

Sie können Argumente nicht nach Namen übergeben, um die Eingabe erforderlicher Argumente zu vermeiden. Sie können nur die optionalen Argumente weglassen.

Sie können ein Parameterarray nicht nach Namen übergeben. Dies liegt daran, dass Sie beim Aufrufen der Prozedur eine unbestimmte Anzahl von durch Kommas getrennten Argumenten für das Parameterarray bereitstellen und der Compiler nicht mehr als ein Argument einem einzelnen Namen zuordnen kann.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameter-Arrays](./parameter-arrays.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
