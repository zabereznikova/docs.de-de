---
title: switch-Ausdruck – C#-Referenz
description: Erfahren Sie, wie Sie den C#-Ausdruck „switch“ für einen Musterabgleich und die Selbstprüfung von Daten verwenden.
ms.date: 01/14/2021
ms.openlocfilehash: 55fef8d351b178fd0ec23847e81e6c56eb1367b0
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536085"
---
# <a name="switch-expression-c-reference"></a>switch-Ausdruck (C#-Referenz)

Im vorliegenden Artikel wird der in C# 8.0 eingeführte `switch`-Ausdruck vorgestellt. Informationen zur `switch`-Anweisung finden Sie im Artikel zur [`switch`-Anweisung](../keywords/switch.md) im Abschnitt zu den [Anweisungen](../keywords/index.md).

## <a name="basic-example"></a>Einfaches Beispiel

Der `switch`-Ausdruck stellt eine ähnliche Semantik wie `switch` im Kontext eines Ausdrucks bereit. Er bietet eine kompakte Syntax, wenn die switch-Verzweigungsarme einen Wert generieren. Das folgende Beispiel zeigt die Struktur eines switch-Ausdrucks. Die Werte aus einem `enum` zur Darstellung visueller Richtungen in einer Onlinekarte entsprechen der jeweiligen Himmelsrichtung:

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetBasicStructure":::

Das vorstehende Beispiel zeigt die grundlegenden Elemente eines switch-Ausdrucks:

- *range-Ausdruck*: Das vorstehende Beispiel verwendet die Variable `direction` als Bereichsausdruck.
- *switch-Ausdrucksverzweigungsarme*: Jeder Verzweigungsarm des switch-Ausdrucks enthält ein *Muster*, einen optionalen *case-Wächter*, das `=>`-Token und einen *Ausdruck*.

Das Ergebnis des *switch-Ausdrucks* ist der Wert des Ausdrucks des ersten *switch-Ausdrucksverzweigungsarms*, dessen *Muster* mit dem des *Bereichsausdrucks* übereinstimmt, und bei dem der *case-Wächter* (sofern vorhanden) als `true` ausgewertet wird. Der *Ausdruck* auf der rechten Seite des `=>`-Tokens kann keine Ausdrucksanweisung sein.

Die *switch-Ausdrucksverzweigungsarme* werden in der Textreihenfolge ausgewertet. Der Compiler gibt einen Fehler aus, wenn ein niedrigerer *switch-Ausdrucksverzweigungsarm* nicht ausgewählt werden kann, weil ein höherer *switch-Ausdrucksverzweigungsarm* allen Werten entspricht.

## <a name="patterns-and-case-guards"></a>Muster und case-Wächter

Viele Muster werden in Verzweigungsarmen von switch-Ausdrücken unterstützt. Das Beispiel oben verwendet ein *Konstantenmuster*. Ein *Konstantenmuster* vergleicht den Bereichsausdruck mit einem Wert. Dieser Wert muss eine Kompilierzeitkonstante sein. Ein *Typmuster* vergleicht den Bereichsausdruck mit einem bekannten Typ. Das folgende Beispiel ruft das dritte Element aus einer Sequenz ab. Basierend auf dem Typ der Sequenz werden unterschiedliche Methoden verwendet:

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetTypePattern":::

Muster können rekursiv sein. Hierbei testet ein Muster einen Typ, und wenn dieser Typ übereinstimmt, gleicht das Muster einen oder mehrere Eigenschaftswerte des Bereichsausdrucks ab. Sie können rekursive Muster verwenden, um das vorstehende Beispiel zu erweitern. Sie fügen switch-Ausdrucksverzweigungsarme für Arrays hinzu, die weniger als 3 Elemente umfassen. Rekursive Muster werden im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetRecursivePattern":::

Rekursive Muster können Eigenschaften des Bereichsausdrucks untersuchen, aber keinen arbiträren Code ausführen. Sie können den in einer `when`-Klausel angegebenen *case-Wächter* verwenden, um ähnliche Überprüfungen für andere Sequenztypen bereitzustellen:

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetGuardCase":::

Schließlich können Sie das `_`-Muster und das `null`-Muster hinzufügen, um Argumente abzufangen, die nicht über einen anderen switch-Ausdrucksverzweigungsarm verarbeitet werden. So wird der switch-Ausdruck *umfassend ausgeschöpft*, d. h. es werden alle möglichen Werte des Bereichsausdrucks behandelt. Das folgende Beispiel fügt diese Ausdrucksverzweigungsarme hinzu:

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetExhaustive":::

Das vorstehende Beispiel fügt ein `null`-Muster hinzu und ändert das `IEnumerable<T>`-Muster in ein `_`-Muster. Das `null`-Muster bietet eine NULL-Überprüfung als switch-Ausdrucksverzweigungsarm. Der Ausdruck für diesen Verzweigungsarm löst eine <xref:System.ArgumentNullException> aus. Das `_`-Muster gleicht alle Eingaben ab, die nicht durch vorherige Verzweigungsarme abgeglichen wurden. Es muss nach der `null`-Überprüfung eingefügt werden, weil es ansonsten die `null`-Eingaben abgleichen würde.

## <a name="non-exhaustive-switch-expressions"></a>Unvollständige switch-Ausdrücke

Wenn keines der switch-Ausdrucksmuster ein Argument abfängt, löst die Runtime eine Ausnahme aus. In .NET Core 3.0 und höher ist die Ausnahme eine <xref:System.Runtime.CompilerServices.SwitchExpressionException?displayProperty=nameWithType>-Klasse. Im .NET Framework ist die Ausnahme eine <xref:System.InvalidOperationException>-Klasse.

## <a name="see-also"></a>Weitere Informationen

- [C#-Spezifikationsvorschlag für rekursive Muster](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression)
- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Mustervergleich](../../pattern-matching.md)
