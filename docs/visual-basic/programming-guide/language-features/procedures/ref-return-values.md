---
title: Ref-Rückgabewerte
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: 2d2a302a899fbde549161469f281d3e580bcb71f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352538"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Unterstützung für Verweis Rückgabewerte (Visual Basic)

Ab C# 7,0 unterstützt die C# Sprache *Verweis Rückgabewerte*. Eine Möglichkeit, Verweis Rückgabewerte zu verstehen, besteht darin, dass Sie das Gegenteil von Argumenten sind, die als Verweis an eine Methode übergebenen werden. Wenn ein als Verweis übergebener Argument geändert wird, werden die Änderungen im Wert der Variablen für den Aufrufer widergespiegelt. Wenn eine Methode einen Verweis Rückgabewert für einen Aufrufer bereitstellt, werden Änderungen, die am Verweis Rückgabewert des Aufrufers vorgenommen werden, in den Daten der aufgerufenen Methode widergespiegelt.

In Visual Basic können keine Methoden mit Verweis Rückgabe Werten erstellt werden, Sie können jedoch Verweis Rückgabewerte verwenden. Anders ausgedrückt: Sie können eine Methode mit einem Verweis Rückgabewert aufrufen und den Rückgabewert ändern, und Änderungen am Verweis Rückgabewert werden in den Daten der aufgerufenen Methode widergespiegelt.

## <a name="modifying-the-ref-return-value-directly"></a>Direktes Ändern des ref-Rückgabewerts

Bei Methoden, die immer erfolgreich sind und über keine `ByRef` Parameter verfügen, können Sie den Verweis Rückgabewert direkt ändern. Dies erreichen Sie, indem Sie den Ausdrücken, die den Verweis Rückgabewert zurückgeben, den neuen Wert zuweisen.

Im folgenden C# Beispiel wird eine `NumericValue.IncrementValue` Methode definiert, die einen internen Wert Inkremente und als Verweis Rückgabewert zurückgibt.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Der Verweis Rückgabewert wird dann vom Aufrufer im folgenden Visual Basic Beispiel geändert. Beachten Sie, dass die Zeile mit dem `NumericValue.IncrementValue`-Methodenaufrufe der-Methode keinen Wert zuweist. Stattdessen wird dem Verweis Rückgabewert, der von der-Methode zurückgegeben wird, ein Wert zugewiesen.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Verwenden einer Hilfsmethode

In anderen Fällen ist es möglicherweise nicht immer wünschenswert, den Verweis Rückgabewert eines Methoden Aufrufes direkt zu ändern. Beispielsweise findet eine Suchmethode, die eine Zeichenfolge zurückgibt, möglicherweise nicht immer eine Entsprechung. In diesem Fall möchten Sie den Verweis Rückgabewert nur ändern, wenn die Suche erfolgreich war.

Dieses Szenario C# wird im folgenden Beispiel veranschaulicht. Er definiert eine `Sentence` Klasse, die C# in geschrieben ist, enthält eine `FindNext` Methode, die das nächste Wort in einem Satz findet, der mit einer angegebenen Teil Zeichenfolge beginnt. Die Zeichenfolge wird als Verweisrückgabewert zurückgegeben, und eine vom Verweis an die Methode übergebene `Boolean`-Variable gibt an, ob die Suche Erfolg hatte. Der Verweis Rückgabewert gibt an, dass der Aufrufer den zurückgegebenen Wert nicht nur lesen kann. Sie kann Sie auch ändern, und diese Änderung wird in den Daten widergespiegelt, die intern in der `Sentence`-Klasse enthalten sind.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Das direkte Ändern des Verweis Rückgabewerts in diesem Fall ist nicht zuverlässig, da der Methodenaufrufe möglicherweise keine Entsprechung findet und das erste Wort im Satz zurückgibt. In diesem Fall wird der Aufrufer versehentlich das erste Wort des Satzes ändern. Dies kann durch den Aufrufer verhindert werden, der eine `null` zurückgibt (oder `Nothing` in Visual Basic). In diesem Fall wird beim Versuch, eine Zeichenfolge zu ändern, deren Wert `Nothing` ist, ein <xref:System.NullReferenceException>ausgelöst. Wenn auch vom Aufrufer verhindert werden kann, der <xref:System.String.Empty?displayProperty=nameWithType>zurückgibt, erfordert dies jedoch, dass der Aufrufer eine Zeichen folgen Variable definiert, deren Wert <xref:System.String.Empty?displayProperty=nameWithType>ist. Der Aufrufer kann diese Zeichenfolge ändern, aber die Änderung selbst ist nicht zweckmäßig, da die geänderte Zeichenfolge keine Beziehung zu den Wörtern in dem Satz hat, der von der `Sentence`-Klasse gespeichert wird.

Die beste Möglichkeit zur Handhabung dieses Szenarios besteht darin, den Verweis Rückgabewert als Verweis an eine Hilfsmethode zu übergeben. Die-Hilfsmethode enthält dann die Logik, um zu bestimmen, ob der Methodenaufrufe erfolgreich war, und, wenn dies der Fall war, um den Verweis Rückgabewert zu ändern. Im folgenden Beispiel wird eine mögliche Implementierung bereitstellt.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Übergeben von Argumenten als Wert und als Verweis](passing-arguments-by-value-and-by-reference.md)
- [Prozeduren in Visual Basic](index.md)
