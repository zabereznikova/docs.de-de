---
title: Fehlertypen
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 04320c7a2fd27749e6de24f0ad21cc51c86ddda2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345155"
---
# <a name="error-types-visual-basic"></a>Fehlertypen (Visual Basic)
In Visual Basic fallen Fehler in eine von drei Kategorien: Syntax Fehler, Laufzeitfehler und logische Fehler.

## <a name="syntax-errors"></a>Syntaxfehler
 *Syntax Fehler* sind solche, die beim Schreiben von Code angezeigt werden. Wenn Sie Visual Studio verwenden, prüft Visual Basic Ihren Code, während Sie ihn im Code- **Editor** -Fenster eingeben, und warnt Sie, wenn Sie einen Fehler auftreten, z. b. falsche Schreibweise eines Worts oder ein sprach Element nicht ordnungsgemäß. Wenn Sie über die Befehlszeile kompilieren, zeigt Visual Basic einen Compilerfehler mit Informationen zum Syntax Fehler an. Syntax Fehler sind die häufigste Art von Fehlern. Sie können Sie problemlos in der Codierungs Umgebung beheben, sobald sie auftreten.

> [!NOTE]
> Die `Option Explicit`-Anweisung ist eine Möglichkeit, Syntax Fehler zu vermeiden. Sie zwingt Sie, im Voraus alle Variablen zu deklarieren, die in der Anwendung verwendet werden sollen. Wenn diese Variablen im Code verwendet werden, werden daher alle typografischen Fehler sofort abgefangen und können korrigiert werden.

## <a name="run-time-errors"></a>Laufzeitfehler
 *Laufzeitfehler* sind solche, die erst angezeigt werden, nachdem Sie den Code kompiliert und ausgeführt haben. Dabei handelt es sich um Code, der möglicherweise korrekt erscheint, da er keine Syntax Fehler aufweist, die jedoch nicht ausgeführt werden. Beispielsweise können Sie ordnungsgemäß eine Codezeile schreiben, um eine Datei zu öffnen. Wenn die Datei jedoch nicht vorhanden ist, kann die Anwendung die Datei nicht öffnen, und es wird eine Ausnahme ausgelöst. Sie können die meisten Laufzeitfehler beheben, indem Sie den fehlerhaften Code umschreiben oder die [Ausnahmebehandlung](../../language-reference/statements/try-catch-finally-statement.md)verwenden und dann erneut kompilieren und wiederholen.
  
## <a name="logic-errors"></a>Logische Fehler
 *Logische Fehler* sind solche, die angezeigt werden, sobald die Anwendung verwendet wird. Sie sind am häufigsten fehlerhafte Annahmen des Entwicklers oder unerwünschte oder unerwartete Ergebnisse als Reaktion auf Benutzeraktionen. Beispielsweise kann eine falsch geschriebene Taste falsche Informationen für eine Methode bereitstellen, oder Sie gehen davon aus, dass ein gültiger Wert immer an eine Methode übergeben wird, wenn dies nicht der Fall ist. Obwohl Logikfehler durch die Verwendung der [Ausnahmebehandlung](../../language-reference/statements/try-catch-finally-statement.md) behandelt werden können (z. b. durch testen, ob ein Argument `Nothing` ist und ein <xref:System.ArgumentNullException>ausgelöst wird), sollten Sie am häufigsten adressiert werden, indem der Fehler in der Logik korrigiert und die Anwendung neu kompiliert wird.

## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Debugger – Grundlagen](/visualstudio/debugger/debugger-feature-tour)
