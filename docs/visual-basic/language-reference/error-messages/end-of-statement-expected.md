---
title: end of-Anweisung erwartet.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 36883989fe5aa0b5c70aa9ab1f7c991fab99e778
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163128"
---
# <a name="bc30205-end-of-statement-expected"></a>BC30205: Ende der Anweisung erwartet.

Die-Anweisung ist syntaktisch abgeschlossen, aber ein zusätzliches Programmier Element folgt dem-Element, das die-Anweisung abschließt. Am Ende jeder Anweisung ist ein Zeichen für den Zeilen Abschluss erforderlich.

 Ein Zeichen für den Zeilen Abschluss dividiert die Zeichen einer Visual Basic Quelldatei in Zeilen. Beispiele für Zeilen Abschluss Zeichen sind das Unicode-Wagen Rücklauf Zeichen (&HD), das Unicode-Zeilenvorschub Zeichen (&ha) und das Unicode-Wagen Rücklauf Zeichen, gefolgt vom Unicode-Zeilenvorschub Zeichen. Weitere Informationen zu Zeilen Abschluss Zeichen finden Sie in der [Visual Basic-Sprachspezifikation](~/_vblang/spec/lexical-grammar.md#line-terminators).

 **Fehler-ID:** BC30205

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie, ob zwei unterschiedliche Anweisungen versehentlich in derselben Zeile abgelegt wurden.

2. Fügen Sie ein Zeilen Abschluss Zeichen nach dem Element ein, das die Anweisung abschließt.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
