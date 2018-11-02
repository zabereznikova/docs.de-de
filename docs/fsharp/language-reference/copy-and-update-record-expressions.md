---
title: Kopieren und Aktualisieren von Datensatzausdrücken (F#)
description: Informationen Sie zum Schreiben von 'kopieren und aktualisieren Datensatz Ausdruck', die einen vorhandenen Datensatz, Updates kopiert Felder angegeben und gibt den aktualisierten Datensatz zurück.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45990842"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="9de8f-103">Kopieren und Aktualisieren von Datensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="9de8f-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="9de8f-104">Ein *kopieren und Aktualisieren des Datensatzes Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt den aktualisierten Datensatz zurück.</span><span class="sxs-lookup"><span data-stu-id="9de8f-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="9de8f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9de8f-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="9de8f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9de8f-106">Remarks</span></span>

<span data-ttu-id="9de8f-107">Datensätze sind standardmäßig unveränderlich, sodass es kein Update einen vorhandenen Datensatz möglich ist.</span><span class="sxs-lookup"><span data-stu-id="9de8f-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="9de8f-108">Um eine aktualisierte Datensatz alle Felder eines Datensatzes erstellen müsste erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9de8f-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="9de8f-109">Zur Vereinfachung dieser Aufgabe eine *kopieren und Aktualisieren des Datensatzes Ausdruck* kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de8f-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="9de8f-110">Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue des gleichen Typs mit angegebenen Felder aus dem Ausdruck und das fehlende Feld, das dem angegebenen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9de8f-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="9de8f-111">Dies kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern.</span><span class="sxs-lookup"><span data-stu-id="9de8f-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="9de8f-112">Nehmen Sie z. B. einen neu erstellten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="9de8f-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="9de8f-113">Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und Aktualisieren des Datensatzes Ausdruck* wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9de8f-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="9de8f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9de8f-114">See also</span></span>

- [<span data-ttu-id="9de8f-115">Datensätze</span><span class="sxs-lookup"><span data-stu-id="9de8f-115">Records</span></span>](records.md)
- [<span data-ttu-id="9de8f-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="9de8f-116">F# Language Reference</span></span>](index.md)
