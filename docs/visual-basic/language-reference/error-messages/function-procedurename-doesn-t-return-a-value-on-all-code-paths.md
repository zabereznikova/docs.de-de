---
title: Die <procedurename>-Funktion gibt nicht für alle Codepfade einen Wert zurück.
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 19b305e337767dfb34718aed7b665f142851bd36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163362"
---
# <a name="bc42105-function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>BC42105: die Funktion " \<procedurename> " gibt nicht für alle Codepfade einen Wert zurück.

Die Funktion " \<procedurename> " gibt nicht für alle Codepfade einen Wert zurück. Fehlt eine Return-Anweisung?

 Eine `Function` Prozedur weist mindestens einen möglichen Pfad durch Ihren Code auf, der keinen Wert zurückgibt.

 Sie können einen Wert aus einer `Function` Prozedur mit einer der folgenden Methoden zurückgeben:

- Fügen Sie den Wert in eine [Return-Anweisung](../statements/return-statement.md)ein.

- Weisen Sie dem Prozedur Namen den Wert zu, `Function` und führen Sie dann eine- `Exit Function` Anweisung aus.

- Weisen Sie dem Prozedur Namen den Wert zu, `Function` und führen Sie dann die `End Function` Anweisung aus.

 Wenn die Steuerung an `Exit Function` oder weitergeleitet `End Function` wird und Sie dem Prozedur Namen keinen Wert zugewiesen haben, gibt die Prozedur den Standardwert des Rückgabe Datentyps zurück. Weitere Informationen finden Sie unter "Verhalten" in der [Function-Anweisung](../statements/function-statement.md).

 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC42105

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung, die eine Rückgabe auslöst, einen Wert zuweisen.

     Es ist einfacher sicherzustellen, dass jede Rückgabe von der Prozedur einen Wert zurückgibt, wenn Sie immer die- `Return` Anweisung verwenden. Wenn Sie dies tun, sollte die letzte Anweisung vor `End Function` eine- `Return` Anweisung sein.

## <a name="see-also"></a>Siehe auch

- [Function-Prozeduren](../../programming-guide/language-features/procedures/function-procedures.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
