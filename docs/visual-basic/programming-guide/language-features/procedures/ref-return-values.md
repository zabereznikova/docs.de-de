---
title: REF-Rückgabewerte (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2979359f0ffafe46a62696485bbb87b211c1704
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651239"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Unterstützung für Rückgabewerte, Referenz (Visual Basic)

C#-7.0 ab, die C#-Sprache unterstützt *verweisen Rückgabewerte*. Eine Möglichkeit, Rückgabewerte Verweis zu verstehen ist, sind das Gegenteil von Argumenten, die als Verweis an eine Methode übergeben werden. Wenn ein als Verweis übergebenes Argument geändert wird, werden die Änderungen im Wert der Variablen für den Aufrufer berücksichtigt. Wenn eine Methode einen Rückgabewert Verweis an einem Aufrufer bereitstellt, sind Änderungen an den der Rückgabewert der Verweis vom Aufrufer in der aufgerufenen Methode Daten widergespiegelt.

Visual Basic lässt nicht zu, Sie auf Autor Methoden mit Verweis Rückgabewerte, aber ermöglicht es Ihnen, Reference-Rückgabewerte zu nutzen. Das heißt, können Sie eine Methode mit einem Rückgabewert Verweis aufrufen und ändern Sie diesen Rückgabewert und Änderungen an der Rückgabewert der Verweis in der aufgerufenen Methode Daten wiedergegeben werden.

## <a name="modifying-the-ref-return-value-directly"></a>Ändern Sie direkt von der Ref-Rückgabewert

Für Methoden, die immer erfolgreich sein und verfügen über keine `ByRef` Parameter, Sie können den Rückgabewert Verweis direkt ändern. Dazu müssen Sie die Ausdrücke, die den Rückgabewert Verweis gibt den neuen Wert zuweisen. 

Im folgenden C#-Beispiel definiert eine `NumericValue.IncrementValue` Rückgabewert der Methode, die einen internen Wert inkrementiert und wird als Verweis zurückgegeben. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Der Verweis zurückzugeben Wert anschließend geändert wird, von dem Aufrufer in der folgenden Visual Basic-Beispiel. Beachten Sie, dass die Zeile mit der `NumericValue.IncrementValue` Methodenaufruf kein an die Methode einen Wert zugewiesen. Stattdessen weist er einen Wert auf den Rückgabewert Verweis, der von der Methode zurückgegeben.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Verwenden eine Hilfsmethode

In anderen Fällen kann den Rückgabewert der Verweis eines Methodenaufrufs direkt ändern immer unerwünscht sein. Beispielsweise kann eine Search-Methode, die eine Zeichenfolge zurückgibt, nicht immer eine Übereinstimmung gefunden werden. In diesem Fall möchten Sie den Rückgabewert der Verweis nur ändern, wenn die Suche erfolgreich ist.

Im folgenden C#-Beispiel wird dieses Szenario veranschaulicht. Definiert eine `Sentence` in c# geschriebene Klasse enthält eine `FindNext` Methode, die das nächste Wort im Satz gefunden werden, die mit einer angegebenen Teilzeichenfolge beginnt. Die Zeichenfolge wird als Verweisrückgabewert zurückgegeben, und eine vom Verweis an die Methode übergebene `Boolean`-Variable gibt an, ob die Suche Erfolg hatte. Der Verweis-Rückgabewert gibt an, dass der Aufrufer nicht den zurückgegebenen Wert schreibgeschützt kann; er oder sie können auch ändern und diese Änderung wirkt sich intern in enthaltenen Daten die `Sentence` Klasse.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Direktes Ändern des Verweis ist der Rückgabewert in diesem Fall nicht zuverlässig ist und seit dem Aufruf der Methode fehlschlagen, um eine Übereinstimmung gefunden, und geben Sie das erste Wort im Satz zurück. In diesem Fall wird der Aufrufer versehentlich das erste Wort des Satzes ändern. Das kann verhindert werden, durch den Aufrufer zurückgeben einer `null` (oder `Nothing` in Visual Basic). Aber in diesem Fall versuchen, eine Zeichenfolge zu ändern, deren Wert `Nothing` löst eine <xref:System.NullReferenceException>. Wenn auch durch den Aufrufer zurückgeben verhindert werden könnte <xref:System.String.Empty?displayProperty=nameWithType>, aber dies erfordert, dass der Aufrufer eine Zeichenfolgenvariable definieren, deren Wert <xref:System.String.Empty?displayProperty=nameWithType>. Während der Aufrufer diese Zeichenfolge ändern kann, dient die Änderung selbst keinen Zweck, da die geänderte Zeichenfolge keine Beziehung zu den Wörtern des Satzes von gespeichert hat die `Sentence` Klasse.

Die beste Möglichkeit, dieses Szenario zu behandeln ist den Rückgabewert der Verweis als Verweis an eine Hilfsmethode zu übergeben. Die Hilfsmethode enthält die Logik, um zu bestimmen, ob der Methodenaufruf erfolgreich war, und wenn dem so wäre, zum Ändern der Verweis Wert zurückgeben. Das folgende Beispiel veranschaulicht eine mögliche Implementierung.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Siehe auch

[Übergeben von Argumenten als Wert und als Verweis](passing-arguments-by-value-and-by-reference.md)   
[Prozeduren in Visual Basic](index.md)   


