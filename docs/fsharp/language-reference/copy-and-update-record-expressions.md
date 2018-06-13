---
title: Kopieren und Update der Datensatz Ausdrücke (f#)
description: Informationen Sie zum Schreiben 'kopieren und Update Datensatz Ausdruck', der einen vorhandenen Datensatz, Updates kopiert Felder angegeben und den aktualisierten Datensatz zurückgegeben.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563058"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="4a294-103">Kopieren und Aktualisieren von Datensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="4a294-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="4a294-104">Ein *kopieren und update der Datensatz Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt die aktualisierte Datensatz zurück.</span><span class="sxs-lookup"><span data-stu-id="4a294-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="4a294-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a294-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="4a294-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a294-106">Remarks</span></span>
<span data-ttu-id="4a294-107">Datensätze sind unveränderlich ist, wird standardmäßig, sodass es kein Update einen vorhandenen Datensatz möglich ist.</span><span class="sxs-lookup"><span data-stu-id="4a294-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="4a294-108">Um eine aktualisierte Datensatz aller Felder eines Datensatzes erstellen müssten erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4a294-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="4a294-109">Um diese Aufgabe zu vereinfachen ein *kopieren und update der Datensatz Ausdruck* kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a294-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="4a294-110">Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue desselben Typs mithilfe des angegebenen Felder aus dem Ausdruck und das fehlende Feld mit dem angegebenen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4a294-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="4a294-111">Dies kann nützlich sein, wenn Sie zum Kopieren eines vorhandenen Datensatzes und möglicherweise einige der Werte der Felder ändern.</span><span class="sxs-lookup"><span data-stu-id="4a294-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="4a294-112">Nehmen Sie z. B. einen neu erstellten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="4a294-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="4a294-113">Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und update der Datensatz Ausdruck* wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4a294-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="4a294-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a294-114">See Also</span></span>
[<span data-ttu-id="4a294-115">Datensätze</span><span class="sxs-lookup"><span data-stu-id="4a294-115">Records</span></span>](records.md)

[<span data-ttu-id="4a294-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4a294-116">F# Language Reference</span></span>](index.md)
