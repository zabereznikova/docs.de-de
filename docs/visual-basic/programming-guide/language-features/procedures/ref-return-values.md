---
title: REF-Rückgabewerte (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: ba649c4beaf3ec70a8c118f823fe8f25651a05a7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198301"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Unterstützung für verweisrückgabewerte (Visual Basic)

Beginnend mit C# 7.0 die C# Abfragesprache unterstützt die *verweisen auf Rückgabewerte*. Eine Möglichkeit, verweisrückgabewerte zu verstehen ist, dass sie das Gegenteil von Argumenten, die durch einen Verweis auf eine Methode übergeben werden. Wenn ein Argument als Verweis übergeben wird, geändert wird, werden die Änderungen der Aufrufer im Wert der Variablen angezeigt. Wenn eine Methode ein verweisrückgabewert an einem Aufrufer bereitstellt, werden Änderungen an der verweisrückgabewert vom Aufrufer in der aufgerufenen Methode Daten wiedergegeben.

Visual Basic erlaubt nicht, Sie zum Erstellen von Methoden mit verweisrückgabewerten Werte zurückgeben, aber es lässt Sie verweisrückgabewerte verarbeiten. Das heißt, können Sie eine Methode mit einem verweisrückgabewert aufrufen und ändern Sie diesen Rückgabewert, und Änderungen an der verweisrückgabewert werden in der aufgerufenen Methode Daten wiedergegeben.

## <a name="modifying-the-ref-return-value-directly"></a>Den Ref-Rückgabewert ändern direkt

Für Methoden, die immer erfolgreich sein und verfügen über keine `ByRef` Parameter, Sie können der verweisrückgabewert direkt ändern. Dazu müssen Sie die Ausdrücke, die der verweisrückgabewert gibt den neuen Wert zuweisen. 

Die folgenden C# Beispiel definiert eine `NumericValue.IncrementValue` Rückgabewert der Methode, die einen internen Wert inkrementiert und wird als Verweis zurückgegeben werden. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Der Verweis zurückgeben, dass ein Wert vom Aufrufer in der folgenden Visual Basic wird anschließend geändert werden. Beachten Sie, dass die Zeile mit der `NumericValue.IncrementValue` Methodenaufruf weist keinen Wert an die Methode. Stattdessen weist es einen Wert, der von der Methode zurückgegebenen verweisrückgabewert.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Mittels einer Hilfsmethode

In anderen Fällen kann der verweisrückgabewert eines Methodenaufrufs direkt ändern nicht immer wünschenswert sein. Beispielsweise kann eine Search-Methode, die eine Zeichenfolge zurückgibt, nicht immer eine Übereinstimmung gefunden werden. Sie möchten in diesem Fall der verweisrückgabewert nur ändern, wenn die Suche erfolgreich ist.

Die folgenden C# Beispiel veranschaulicht dieses Szenario. Definiert eine `Sentence` in geschriebenen Klasse C# umfasst eine `FindNext` Methode, die das nächste Wort im Satz gefunden wird, die mit einer angegebenen Teilzeichenfolge beginnt. Die Zeichenfolge wird als Verweisrückgabewert zurückgegeben, und eine vom Verweis an die Methode übergebene `Boolean`-Variable gibt an, ob die Suche Erfolg hatte. Der Verweis-Rückgabewert gibt an, dass der Aufrufer den zurückgegebenen Wert nicht nur lesen kann; er oder sie können auch ändern, es, und diese Änderung wirkt sich die Daten intern in der `Sentence` Klasse.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Direktes Ändern des Verweis ist der Rückgabewert in diesem Fall nicht zuverlässig, da der Aufruf der Methode möglicherweise keine Übereinstimmung gefunden, und geben Sie das erste Wort im Satz zurück. In diesem Fall wird der Aufrufer nicht versehentlich das erste Wort des Satzes ändern. Dies kann verhindert werden, durch den Aufrufer zurückgeben einer `null` (oder `Nothing` in Visual Basic). Aber in diesem Fall versucht, eine Zeichenfolge, deren Wert `Nothing` löst eine <xref:System.NullReferenceException>. Wenn auch durch den Aufrufer zurückgeben verhindert werden könnte <xref:System.String.Empty?displayProperty=nameWithType>, aber dies erfordert, dass der Aufrufer eine String-Variable definieren, deren Wert <xref:System.String.Empty?displayProperty=nameWithType>. Während der Aufrufer diese Zeichenfolge nicht ändern kann, dient die Änderung selbst keinen Zweck, da die geänderte Zeichenfolge keine Beziehung zu den Wörtern in den Satz von gespeichert hat die `Sentence` Klasse.

Die beste Methode zum Behandeln dieses Szenarios ist der verweisrückgabewert als Verweis an eine Hilfsmethode zu übergeben. Die Hilfsmethode enthält die Logik, um zu bestimmen, ob der Methodenaufruf erfolgreich war, und wenn dies der Fall ist, zum Ändern der verweisrückgabewert. Im folgenden Beispiel wird eine mögliche Implementierung.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Siehe auch

[Übergeben von Argumenten als Wert und als Verweis](passing-arguments-by-value-and-by-reference.md)   
[Prozeduren in Visual Basic](index.md)   


