---
title: Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert wurden.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: a2277e3778c2c252fd4b1eaeb033d549f041c15c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160632"
---
# <a name="bc31122-custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>BC31122: der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne explizite Delegattypen deklariert werden.

Anders als bei einem Nichtbenutzer definierten Ereignis, erfordert eine- `Custom Event` Deklaration eine- `As` Klausel, die dem Ereignis Namen folgt, der explizit den Delegattyp für das Ereignis angibt.

 Nichtbenutzer definierte Ereignisse können entweder mit einer `As` -Klausel und einem expliziten Delegattyp oder mit einer Parameterliste direkt nach dem Ereignis Namen definiert werden.

 **Fehler-ID:** BC31122

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Definieren Sie einen Delegaten mit der gleichen Parameterliste wie das benutzerdefinierte Ereignis.

     Wenn z. b `Custom Event` . von definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , würde der entsprechende Delegat wie folgt lauten.

     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]

2. Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses durch eine- `As` Klausel, die den Delegattyp angibt.

     Wenn Sie mit dem Beispiel fortfahren, `Custom Event` wird die Deklaration wie folgt umgeschrieben.

     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]

## <a name="example"></a>Beispiel

 In diesem Beispiel wird eine deklariert `Custom Event` und die erforderliche- `As` Klausel mit einem Delegattyp angegeben.

 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Event-Anweisung](../statements/event-statement.md)
- [Delegate-Anweisung](../statements/delegate-statement.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
