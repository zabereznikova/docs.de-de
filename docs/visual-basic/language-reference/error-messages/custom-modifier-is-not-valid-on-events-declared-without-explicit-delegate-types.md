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
# <a name="bc31122-custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="b9ec8-102">BC31122: der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne explizite Delegattypen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-102">BC31122: 'Custom' modifier is not valid on events declared without explicit delegate types</span></span>

<span data-ttu-id="b9ec8-103">Anders als bei einem Nichtbenutzer definierten Ereignis, erfordert eine- `Custom Event` Deklaration eine- `As` Klausel, die dem Ereignis Namen folgt, der explizit den Delegattyp für das Ereignis angibt.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>

 <span data-ttu-id="b9ec8-104">Nichtbenutzer definierte Ereignisse können entweder mit einer `As` -Klausel und einem expliziten Delegattyp oder mit einer Parameterliste direkt nach dem Ereignis Namen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>

 <span data-ttu-id="b9ec8-105">**Fehler-ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="b9ec8-105">**Error ID:** BC31122</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b9ec8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b9ec8-106">To correct this error</span></span>

1. <span data-ttu-id="b9ec8-107">Definieren Sie einen Delegaten mit der gleichen Parameterliste wie das benutzerdefinierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-107">Define a delegate with the same parameter list as the custom event.</span></span>

     <span data-ttu-id="b9ec8-108">Wenn z. b `Custom Event` . von definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , würde der entsprechende Delegat wie folgt lauten.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>

     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]

2. <span data-ttu-id="b9ec8-109">Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses durch eine- `As` Klausel, die den Delegattyp angibt.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>

     <span data-ttu-id="b9ec8-110">Wenn Sie mit dem Beispiel fortfahren, `Custom Event` wird die Deklaration wie folgt umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>

     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]

## <a name="example"></a><span data-ttu-id="b9ec8-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9ec8-111">Example</span></span>

 <span data-ttu-id="b9ec8-112">In diesem Beispiel wird eine deklariert `Custom Event` und die erforderliche- `As` Klausel mit einem Delegattyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9ec8-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>

 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]

## <a name="see-also"></a><span data-ttu-id="b9ec8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9ec8-113">See also</span></span>

- [<span data-ttu-id="b9ec8-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9ec8-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="b9ec8-115">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9ec8-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="b9ec8-116">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b9ec8-116">Events</span></span>](../../programming-guide/language-features/events/index.md)
