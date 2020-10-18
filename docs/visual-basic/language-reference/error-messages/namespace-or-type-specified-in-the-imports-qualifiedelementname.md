---
title: Der in Imports '<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 284a8c71fee8835f78ca5435932819fded1b1f30
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160131"
---
# <a name="bc40056-namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>BC40056: der Namespace oder Typ, der in den Importen ' ' angegeben ist, \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden.

Der in den Importen ' ' angegebene Namespace oder Typ \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält. Stellen Sie sicher, dass der Alias Name keine anderen Aliase enthält.

Eine- `Imports` Anweisung gibt ein enthaltende Element an, das entweder nicht gefunden werden kann oder keine Member definiert `Public` .

Ein *enthaltende Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein. Das enthaltende Element enthält Member, z. b. Variablen, Prozeduren oder andere enthaltende Elemente.

Der Zweck des Importierens besteht darin, dass Ihr Code auf Namespaces oder Typmember zugreifen kann, ohne Sie qualifizieren zu müssen. Das Projekt muss möglicherweise auch einen Verweis auf den Namespace oder den Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Wenn der Compiler das angegebene enthaltende Element nicht finden kann, kann er keine Verweise auflösen, die ihn verwenden. Wenn das-Element gefunden wird, aber das-Element keine Member verfügbar macht `Public` , kann kein Verweis erfolgreich sein. In beiden Fällen ist es bedeutungslos, das-Element zu importieren.

Beachten Sie, dass Sie, wenn Sie ein enthaltenes Element importieren und ihm einen importieralias zuweisen, diesen Importalias nicht verwenden können, um ein anderes Element zu importieren. Der folgende Code generiert einen Compilerfehler.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**Fehler-ID:** BC40056

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass das enthaltende Element über Ihr Projekt zugänglich ist.

2. Vergewissern Sie sich, dass die Spezifikation des enthaltenden Elements keinen importtalias aus einem anderen Import enthält.

3. Vergewissern Sie sich, dass das enthaltende Element mindestens einen Member verfügbar macht `Public` .

## <a name="see-also"></a>Siehe auch

- [Imports-Anweisung (.NET-Namespace und Typ)](../statements/imports-statement-net-namespace-and-type.md)
- [Namespace-Anweisung](../statements/namespace-statement.md)
- [Öffentlich](../modifiers/public.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
