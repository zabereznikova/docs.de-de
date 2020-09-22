---
title: end of-Anweisung erwartet.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 9141400afc651629df381e0a655e2d7b9da2e45d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874425"
---
# <a name="end-of-statement-expected"></a>end of-Anweisung erwartet.

Die-Anweisung ist syntaktisch abgeschlossen, aber ein zusätzliches Programmier Element folgt dem-Element, das die-Anweisung abschließt. Am Ende jeder Anweisung ist ein Zeichen für den Zeilen Abschluss erforderlich.
  
 Ein Zeichen für den Zeilen Abschluss dividiert die Zeichen einer Visual Basic Quelldatei in Zeilen. Beispiele für Zeilen Abschluss Zeichen sind das Unicode-Wagen Rücklauf Zeichen (&HD), das Unicode-Zeilenvorschub Zeichen (&ha) und das Unicode-Wagen Rücklauf Zeichen, gefolgt vom Unicode-Zeilenvorschub Zeichen. Weitere Informationen zu Zeilen Abschluss Zeichen finden Sie in der [Visual Basic-Sprachspezifikation](~/_vblang/spec/lexical-grammar.md#line-terminators).
  
 **Fehler-ID:** BC30205
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler
  
1. Überprüfen Sie, ob zwei unterschiedliche Anweisungen versehentlich in derselben Zeile abgelegt wurden.
  
2. Fügen Sie ein Zeilen Abschluss Zeichen nach dem Element ein, das die Anweisung abschließt.
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
