---
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346754"
---
# <a name="property-statement"></a>Property Statement

Deklariert den Namen einer Eigenschaft sowie die Eigenschaften Prozeduren, die zum Speichern und Abrufen des Werts der Eigenschaft verwendet werden.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>-Komponenten

- `attributelist`

  Optional. Liste der Attribute, die für diese Eigenschaft oder `Get` oder `Set` Prozedur gelten. Siehe [Attribut Liste](attribute-list.md).

- `Default`

  Optional. Gibt an, dass diese Eigenschaft die Standard Eigenschaft für die Klasse oder Struktur ist, in der Sie definiert ist. Standardeigenschaften müssen Parameter akzeptieren und können ohne Angabe des Eigenschaften namensfest gelegt und abgerufen werden. Wenn Sie die Eigenschaft als `Default`deklarieren, können Sie `Private` nicht für die Eigenschaft oder für eine der Eigenschaften Prozeduren verwenden.

- `accessmodifier`

  Optional für die `Property`-Anweisung und für höchstens eine der Anweisungen `Get` und `Set`. Einer der folgenden Werte ist möglich:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Optional. Einer der folgenden Werte ist möglich:

  - [Overloads](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overrides](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Optional. Siehe [Shared](../modifiers/shared.md).

- `Shadows`

  Optional. Siehe [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  Optional. Siehe [nur](../modifiers/readonly.md)lesen.

- `WriteOnly`

  Optional. Siehe [nur](../modifiers/writeonly.md)schreiben.

- `Iterator`

  Optional. Siehe [Iterator](../modifiers/iterator.md).

- `name`

  Erforderlich Der Name der Eigenschaft. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Optional. Liste der Namen der lokalen Variablen, die die Parameter dieser Eigenschaft darstellen, sowie mögliche zusätzliche Parameter der `Set` Prozedur. Siehe [Parameter Liste](parameter-list.md).

- `returntype`

  Erforderlich, wenn `Option Strict` `On`ist. Datentyp des Werts, der von dieser Eigenschaft zurückgegeben wird.

- `Implements`

  Optional. Gibt an, dass diese Eigenschaft eine oder mehrere Eigenschaften implementiert, von denen jede in einer Schnittstelle definiert ist, die von der enthaltenden Klasse oder Struktur dieser Eigenschaft implementiert wird. Siehe [implementierende Anweisung](implements-statement.md).

- `implementslist`

  Erforderlich, wenn `Implements` angegeben wird. Liste der implementierten Eigenschaften.

  `implementedproperty [ , implementedproperty ... ]`

  Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:

  `interface.definedname`

  |-Komponente|Beschreibung|
  |---|---|
  |`interface`|Erforderlich Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Eigenschaft implementiert wird.|
  |`definedname`|Erforderlich Der Name, mit dem die Eigenschaft in `interface`definiert wird.|

- `Get`

  Optional. Erforderlich, wenn die Eigenschaft als `ReadOnly`gekennzeichnet ist. Startet eine `Get`-Eigenschaften Prozedur, die verwendet wird, um den Wert der-Eigenschaft zurückzugeben.  Die `Get`-Anweisung wird nicht mit [automatisch implementierten Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md)verwendet.

- `statements`

  Optional. Block von Anweisungen, die innerhalb des `Get` oder `Set` Prozedur ausgeführt werden sollen.

- `End Get`

  Beendet die `Get`-Eigenschaften Prozedur.

- `Set`

  Optional. Erforderlich, wenn die Eigenschaft als `WriteOnly`gekennzeichnet ist. Startet eine `Set`-Eigenschaften Prozedur, die zum Speichern des Werts der-Eigenschaft verwendet wird.  Die `Set`-Anweisung wird nicht mit [automatisch implementierten Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md)verwendet.

- `End Set`

  Beendet die `Set`-Eigenschaften Prozedur.

- `End Property`

  Beendet die Definition dieser Eigenschaft.

## <a name="remarks"></a>Hinweise

Mit der `Property`-Anweisung wird die Deklaration einer Eigenschaft eingeführt. Eine Eigenschaft kann über eine `Get` Prozedur (schreibgeschützt), eine `Set` Prozedur (schreibgeschützt) oder beides (Lese-/Schreibzugriff) verfügen. Wenn Sie eine automatisch implementierte Eigenschaft verwenden, können Sie die `Get` und `Set` Verfahren weglassen. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

Sie können `Property` nur auf Klassenebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für eine Eigenschaft eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und nicht eine Quelldatei, ein Namespace, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Standardmäßig verwenden Eigenschaften öffentlichen Zugriff. Sie können die Zugriffsebene einer Eigenschaft mit einem Zugriffsmodifizierer für die `Property`-Anweisung anpassen, und Sie können optional eine ihrer Eigenschaften Prozeduren auf eine restriktivere Zugriffsebene anpassen.

Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften Zuweisungen. Wenn Sie keinen Parameter für `Set`bereitstellen, verwendet die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) einen impliziten Parameter mit dem Namen `value`. Dieser Parameter enthält den Wert, der der Eigenschaft zugewiesen werden soll. In der Regel speichern Sie diesen Wert in einer privaten lokalen Variable und geben ihn zurück, wenn die `Get` Prozedur aufgerufen wird.

## <a name="rules"></a>Regeln

- **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene für die `Get` oder die `Set` Prozedur angeben, jedoch nicht für beide. Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft. Wenn die Eigenschaft beispielsweise als `Friend`deklariert ist, können Sie die `Set` Prozedur `Private`deklarieren, jedoch nicht `Public`.

  Wenn Sie eine `ReadOnly`-oder `WriteOnly`-Eigenschaft definieren, stellt die Prozedur (`Get` oder `Set`) der einzelnen Eigenschaft die gesamte-Eigenschaft dar. Sie können für eine solche Prozedur keine andere Zugriffsebene deklarieren, da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.

- **Rückgabetyp.** Die `Property`-Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.

  Wenn Sie `returntype`nicht angeben, gibt die-Eigenschaft `Object`zurück.

- **Ausführungs.** Wenn diese Eigenschaft das `Implements`-Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur direkt nach der `Class`-oder `Structure` Anweisung eine `Implements`-Anweisung aufweisen. Die `Implements`-Anweisung muss jede in `implementslist`angegebene Schnittstelle enthalten. Der Name, mit dem eine Schnittstelle die `Property` definiert (in `definedname`), muss jedoch nicht mit dem Namen dieser Eigenschaft (in `name`) identisch sein.

## <a name="behavior"></a>Verhalten

- **Zurückgeben von einer Eigenschaften Prozedur.** Wenn die `Get` oder `Set` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung nach der Anweisung fortgesetzt, die Sie aufgerufen hat.

  Die Anweisungen `Exit Property` und `Return` führen zu einem sofortigen Beenden einer Eigenschaften Prozedur. Eine beliebige Anzahl von `Exit Property`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Property`-und `Return`-Anweisungen mischen.

- **Rückgabewert.** Um einen Wert aus einer `Get` Prozedur zurückzugeben, können Sie den Wert entweder dem Eigenschaftsnamen zuweisen oder ihn in eine `Return` Anweisung einschließen. Im folgenden Beispiel wird der-Rückgabewert dem Eigenschaftsnamen `quoteForTheDay` zugewiesen und dann die `Exit Property`-Anweisung verwendet, um zurückzugeben.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Wenn Sie `Exit Property` verwenden, ohne `name`einen Wert zuzuweisen, gibt die `Get`-Prozedur den Standardwert für den Datentyp der Eigenschaft zurück.

  Die Anweisung `Return` gleichzeitig weist den `Get` Prozedur Rückgabewert zu und beendet die Prozedur. Dies wird im folgenden Beispiel veranschaulicht.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine-Eigenschaft in einer-Klasse deklariert.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>Siehe auch

- [Automatisch implementierte Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
- [Get-Anweisung](get-statement.md)
- [Set-Anweisung](set-statement.md)
- [Parameterliste](parameter-list.md)
- [Default](../modifiers/default.md)
