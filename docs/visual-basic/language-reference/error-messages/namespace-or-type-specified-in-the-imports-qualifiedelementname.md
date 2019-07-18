---
title: Der in Imports '<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 1873c0af7a251afd7754557f5dcb6aed13eb9f11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918319"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Namespace oder Typ angegeben werden, in Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden

Namespace oder Typ angegeben werden, in Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält. Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.

Ein `Imports` Anweisung gibt ein enthaltendes Element, das entweder nicht gefunden werden kann, oder keine definiert `Public` Member.

Ein *, das Element enthält* -Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein kann. Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere Elemente enthält.

Importieren von dient zu Ihrem Code, um Namespaces oder Typs auf Member zuzugreifen, ohne sie zu qualifizieren. Ihr Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Wenn der Compiler das angegebene Element enthält, nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden. Wenn das Element gefunden wird, das Element macht aber keine `Public` Elemente, und klicken Sie dann auf keinen Verweis kann erfolgreich sein. In beiden Fällen ist es ohne Bedeutung für das Element zu importieren.

Sollten Sie bedenken, wenn Sie ein enthaltenden Element importieren und weisen Sie einen Importalias zu, klicken Sie dann Sie diesen Importalias nicht verwenden, um ein anderes Element zu importieren. Der folgende Code generiert einen Compilerfehler.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**Fehler-ID:** BC40056

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt möglich ist.

2. Stellen Sie sicher, dass die Spezifikation des enthaltenden Elements Importalias einen weiteren Importvorgang nicht enthalten ist.

3. Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.

## <a name="see-also"></a>Siehe auch

- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
