---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Erfahren Sie, wie Sie einen "Kopieren und aktualisieren"-Ausdruck schreiben, der einen vorhandenen Datensatz oder einen anonymen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten Datensatz oder anonymen Datensatz zurückgibt.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630375"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="1c99c-103">Kopieren und Aktualisieren von Datensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="1c99c-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="1c99c-104">Ein *Kopier-und Update Daten Satz Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten Datensatz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1c99c-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c99c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c99c-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="1c99c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c99c-106">Remarks</span></span>

<span data-ttu-id="1c99c-107">Datensätze und anonyme Datensätze sind standardmäßig unveränderlich, sodass kein Update eines vorhandenen Datensatzes möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1c99c-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="1c99c-108">Zum Erstellen eines aktualisierten Datensatzes müssten alle Felder eines Datensatzes erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c99c-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="1c99c-109">Um diese Aufgabe zu vereinfachen, kann ein *Kopier-und Update Ausdruck* verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c99c-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="1c99c-110">Dieser Ausdruck nimmt einen vorhandenen Datensatz an, erstellt einen neuen desselben Typs, indem er die angegebenen Felder aus dem Ausdruck und das fehlende Feld verwendet, das durch den Ausdruck angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1c99c-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="1c99c-111">Dies kann hilfreich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="1c99c-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="1c99c-112">Nehmen Sie zum Beispiel einen neu erstellten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="1c99c-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="1c99c-113">Wenn Sie nur ein Feld dieses Datensatzes aktualisieren möchten, können Sie den *Ausdruck zum Kopieren und Aktualisieren von Datensätzen* wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="1c99c-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="1c99c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c99c-114">See also</span></span>

- [<span data-ttu-id="1c99c-115">Datensätze</span><span class="sxs-lookup"><span data-stu-id="1c99c-115">Records</span></span>](records.md)
- [<span data-ttu-id="1c99c-116">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="1c99c-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="1c99c-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="1c99c-117">F# Language Reference</span></span>](index.md)
