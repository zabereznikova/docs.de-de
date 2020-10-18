---
title: Die <variablename>-Variable wird verwendet, bevor ihr ein Wert zugewiesen wird.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 6db8626701267f2051b289b267e7b2d9da51c283
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162218"
---
# <a name="bc42104-variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>BC42104: die Variable ' \<variablename> ' wird verwendet, bevor ihr ein Wert zugewiesen wurde.

Die-Variable \<variablename> wird verwendet, bevor ihr ein Wert zugewiesen wurde. Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.

 Eine Anwendung verfügt über mindestens einen möglichen Pfad durch Ihren Code, der eine Variable liest, bevor ihr ein Wert zugewiesen wird.

 Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp. Bei Verweisdatentypen ist dieser Standardwert [Nothing](../nothing.md). Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.

 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC42104

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine beliebige Anweisung weitergeleitet wird.

- Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist die Initialisierung im Rahmen der Deklaration. Siehe "Initialisierung" in der [Dim-Anweisung](../statements/dim-statement.md).

## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../statements/dim-statement.md)
- [Variablen Deklaration](../../programming-guide/language-features/variables/variable-declaration.md)
- [Problembehandlung bei Variablen](../../programming-guide/language-features/variables/troubleshooting-variables.md)
