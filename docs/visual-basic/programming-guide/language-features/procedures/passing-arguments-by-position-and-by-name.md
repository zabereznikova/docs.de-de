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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352620"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Übergeben von Argumenten nach Position und Name (Visual Basic)

Wenn Sie eine `Sub` oder `Function` Prozedur aufzurufen, können Sie Argumente *nach Position* – in der Reihenfolge übergeben, in der Sie in der Definition der Prozedur angezeigt werden – oder Sie können Sie ohne Berücksichtigung der Position *nach Namen*übergeben.

Wenn Sie ein Argument anhand des Namens übergeben, geben Sie den deklarierten Namen des Arguments an, gefolgt von einem Doppelpunkt und einem Gleichheitszeichen (`:=`), gefolgt vom Argument Wert. Sie können benannte Argumente in beliebiger Reihenfolge angeben.

Die folgende `Sub` Prozedur nimmt z. b. drei Argumente an:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Wenn Sie diese Prozedur aufzurufen, können Sie die Argumente nach Position, Name oder mithilfe einer Kombination aus beidem bereitstellen.

## <a name="passing-arguments-by-position"></a>Übergeben von Argumenten nach Position

Sie können die `Display`-Methode mit den als Position weiter gegebenen Argumenten und durch Kommas getrennt, wie im folgenden Beispiel gezeigt:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Wenn Sie ein optionales Argument in einer Liste von Positions Argumenten weglassen, müssen Sie den Platz mit einem Komma ablegen. Im folgenden Beispiel wird die `Display`-Methode ohne das `age`-Argument aufgerufen:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Übergeben von Argumenten nach Name

Alternativ können Sie `Display` mit den über den Namen weiter gegebenen Argumenten (auch durch Kommas getrennt) aufzurufen, wie im folgenden Beispiel gezeigt:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Das übergeben von Argumenten nach Namen auf diese Weise ist besonders nützlich, wenn Sie eine Prozedur mit mehr als einem optionalen Argument aufgerufen haben. Wenn Sie Argumente nach Namen angeben, müssen Sie keine aufeinander folgenden Kommas verwenden, um fehlende Positions Argumente anzugeben. Durch die Übergabe von Argumenten nach Name können Sie auch leichter nachverfolgen, welche Argumente Sie übergeben und welche nicht.

## <a name="mixing-arguments-by-position-and-by-name"></a>Mischen von Argumenten nach Position und Name

Sie können Argumente sowohl nach Position als auch nach Name in einem einzelnen Prozedur Befehl angeben, wie im folgenden Beispiel gezeigt:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

Im vorherigen Beispiel ist kein zusätzliches Komma erforderlich, um die Position des ausgelassenen `age` Arguments aufzunehmen, da `birth` nach Name übermittelt wird.

Wenn Sie in Versionen von Visual Basic vor 15,5, wenn Sie Argumente durch eine Mischung aus Position und Name angeben, müssen die Positions Argumente zuerst alle auftreten. Nachdem Sie ein Argument nach Namen angegeben haben, müssen alle verbleibenden Argumente als Name übergeben werden.  Der `Display` folgende-Befehl zeigt beispielsweise den Compilerfehler [BC30241: das benannte Argument wurde erwartet](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Ab Visual Basic 15,5 können Positions Argumente benannte Argumente folgen, wenn sich die abschließenden Positions Argumente an der richtigen Position befinden. Bei der Kompilierung unter Visual Basic 15,5 wird der vorherige-Befehl der `Display`-Methode erfolgreich kompiliert und generiert nicht mehr den Compilerfehler [BC30241](../../../misc/bc30241.md).

Diese Möglichkeit, benannte und Positions Argumente in beliebiger Reihenfolge zu mischen und abzugleichen, ist besonders nützlich, wenn Sie ein benanntes Argument verwenden möchten, um den Code lesbarer zu machen. Der folgende `Person` Klassenkonstruktor benötigt z. b. zwei Argumente des Typs `Person`, die beide `Nothing`werden können.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

Wenn Sie gemischte benannte und Positions Argumente verwenden, ist es hilfreich, den Zweck des Codes klar zu machen, wenn der Wert des `father`-und `mother` Arguments `Nothing`ist:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Wenn Sie Positions Argumenten mit benannten Argumenten folgen möchten, müssen Sie das folgende-Element der Visual Basic Project-Datei (\*. vbproj) hinzufügen:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Einschränkungen beim Bereitstellen von Argumenten nach Namen

Sie können keine Argumente nach Namen übergeben, um zu vermeiden, dass erforderliche Argumente eingegeben werden. Sie können nur die optionalen Argumente weglassen.

Ein Parameter Array kann nicht anhand des Namens übergeben werden. Dies liegt daran, dass beim Aufrufen der Prozedur eine unbegrenzte Anzahl von Komma getrennten Argumenten für das Parameter Array bereitgestellt wird, und der Compiler kann nicht mehr als ein Argument mit einem einzelnen Namen zuordnen.

## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
