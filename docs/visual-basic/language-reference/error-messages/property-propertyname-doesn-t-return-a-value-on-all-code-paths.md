---
title: 'Die <propertyname>-Eigenschaft gibt nicht für alle Codepfade einen Wert zurück:'
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 0736e2cbcdea1422d40161c88f898d487f72e3bc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162387"
---
# <a name="bc42107-property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>BC42107: die Eigenschaft " \<propertyname> " gibt nicht für alle Codepfade einen Wert zurück.

Die-Eigenschaft \<propertyname> gibt nicht für alle Codepfade einen Wert zurück. Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.

Eine Eigenschaften `Get` Prozedur weist mindestens einen möglichen Pfad durch Ihren Code auf, der keinen Wert zurückgibt.

 Sie können einen Wert aus einer Eigenschaften `Get` Prozedur mit einer der folgenden Methoden zurückgeben:

- Weisen Sie dem Eigenschaftsnamen den Wert zu, und führen Sie dann eine- `Exit Property` Anweisung aus.

- Weisen Sie dem Eigenschaftsnamen den Wert zu, und führen Sie dann die `End Get` Anweisung aus.

- Fügen Sie den Wert in eine [Return-Anweisung](../statements/return-statement.md)ein.

Wenn die Steuerung an `Exit Property` oder weitergeleitet `End Get` wird und Sie dem Eigenschaftsnamen keinen Wert zugewiesen haben, `Get` gibt die Prozedur den Standardwert des Datentyps der Eigenschaft zurück. Weitere Informationen finden Sie unter "Verhalten" in der [Function-Anweisung](../statements/function-statement.md).

Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Fehler-ID:** BC42107

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung, die eine Rückgabe auslöst, einen Wert zuweisen.

  Es ist einfacher sicherzustellen, dass jede Rückgabe von der Prozedur einen Wert zurückgibt, wenn Sie immer die- `Return` Anweisung verwenden. Wenn Sie dies tun, sollte die letzte Anweisung vor `End Get` eine- `Return` Anweisung sein.

## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Get-Anweisung](../statements/get-statement.md)
