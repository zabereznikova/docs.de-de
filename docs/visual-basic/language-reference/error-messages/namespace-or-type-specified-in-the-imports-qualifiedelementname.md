---
title: Der in Imports '<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8675d9c3b202200c89e12e7a5f51a19d9e3e0e64
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409464"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Der in Imports '\<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden

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

## <a name="see-also"></a>Weitere Informationen

- [Imports-Anweisung (.NET-Namespace und Typ)](../statements/imports-statement-net-namespace-and-type.md)
- [Namespace-Anweisung](../statements/namespace-statement.md)
- [Öffentlich](../modifiers/public.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
