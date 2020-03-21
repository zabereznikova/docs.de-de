---
title: Ref-Rückgabewerte
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186937"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Unterstützung für Referenzrückgabewerte (Visual Basic)

Beginnend mit C-7.0 unterstützt die Sprache *C-Sprache Referenzrückgabewerte*. Eine Möglichkeit, Referenzrückgabewerte zu verstehen, besteht darin, dass sie das Gegenteil von Argumenten sind, die durch Verweis auf eine Methode übergeben werden. Wenn ein argument, das durch Verweis übergeben wird, geändert wird, werden die Änderungen im Wert der Variablen auf dem Aufrufer widergespiegelt. Wenn eine Methode einen Verweisrückgabewert für einen Aufrufer bereitstellt, werden Änderungen, die vom Aufrufer am Verweisrückgabewert vorgenommen wurden, in den Daten der aufgerufenen Methode widergespiegelt.

Visual Basic ermöglicht es Ihnen nicht, Methoden mit Verweisrückgabewerten zu erstellen, aber es erlaubt Ihnen, Referenzrückgabewerte zu verwenden. Mit anderen Worten, Sie können eine Methode mit einem Referenzrückgabewert aufrufen und diesen Rückgabewert ändern, und Änderungen am Referenzrückgabewert werden in den Daten der aufgerufenen Methode widergespiegelt.

## <a name="modifying-the-ref-return-value-directly"></a>Direktes Ändern des Ref-Rückgabewerts

Bei Methoden, die immer `ByRef` erfolgreich sind und keine Parameter haben, können Sie den Referenzrückgabewert direkt ändern. Dazu weisen Sie den neuen Wert den Ausdrücken zu, die den Referenzrückgabewert zurückgeben.

Im folgenden Beispiel definiert `NumericValue.IncrementValue` das Beispiel "C" eine Methode, die einen internen Wert erhöht und als Referenzrückgabewert zurückgibt.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Der Referenzrückgabewert wird dann vom Aufrufer im folgenden Visual Basic-Beispiel geändert. Beachten Sie, dass `NumericValue.IncrementValue` die Zeile mit dem Methodenaufruf der Methode keinen Wert zuweist. Stattdessen wird dem von der Methode zurückgegebenen Referenzrückgabewert ein Wert zugewiesen.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Verwenden einer Hilfsmethode

In anderen Fällen ist es möglicherweise nicht immer wünschenswert, den Referenzrückgabewert eines Methodenaufrufs direkt zu ändern. Beispielsweise findet eine Suchmethode, die eine Zeichenfolge zurückgibt, möglicherweise nicht immer eine Übereinstimmung. In diesem Fall möchten Sie den Referenzrückgabewert nur ändern, wenn die Suche erfolgreich ist.

Dieses Szenario wird im folgenden Beispiel veranschaulicht. Es definiert `Sentence` eine Klasse, die `FindNext` in C- geschrieben ist, enthält eine Methode, die das nächste Wort in einem Satz findet, der mit einer angegebenen Teilzeichenfolge beginnt. Die Zeichenfolge wird als Verweisrückgabewert zurückgegeben, und eine vom Verweis an die Methode übergebene `Boolean`-Variable gibt an, ob die Suche Erfolg hatte. Der Referenzrückgabewert gibt an, dass der Aufrufer ihn nicht nur lesen kann, sondern auch ändern `Sentence` kann, und dass diese Änderung in den intern in der Klasse enthaltenen Daten widergespiegelt wird.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Das direkte Ändern des Referenzrückgabewerts ist in diesem Fall nicht zuverlässig, da der Methodenaufruf möglicherweise keine Übereinstimmung findet und das erste Wort im Satz zurückgibt. In diesem Fall ändert der Aufrufer versehentlich das erste Wort des Satzes. Dies kann verhindert werden, `null` indem `Nothing` der Aufrufer eine (oder in Visual Basic) zurückgibt. In diesem Fall wird jedoch versucht, eine `Nothing` Zeichenfolge <xref:System.NullReferenceException>zu ändern, deren Wert eine . Wenn auch durch die Rückgabe <xref:System.String.Empty?displayProperty=nameWithType>des Aufrufers verhindert werden könnte, erfordert <xref:System.String.Empty?displayProperty=nameWithType>dies jedoch, dass der Aufrufer eine Zeichenfolgenvariable definiert, deren Wert . Während der Aufrufer diese Zeichenfolge ändern kann, hat die Änderung selbst keinen Zweck, da die `Sentence` geänderte Zeichenfolge keine Beziehung zu den Wörtern in dem von der Klasse gespeicherten Satz hat.

Die beste Methode, dieses Szenario zu behandeln, besteht darin, den Referenzrückgabewert als Verweis auf eine Hilfsmethode zu übergeben. Die Hilfsmethode enthält dann die Logik, um zu bestimmen, ob der Methodenaufruf erfolgreich war, und, falls dies der Derentumso, den Verweisrückgabewert zu ändern. Im folgenden Beispiel wird eine mögliche Implementierung angezeigt.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- [Übergeben von Argumenten nach Wert und Verweis](passing-arguments-by-value-and-by-reference.md)
- [Prozeduren in Visual Basic](index.md)
