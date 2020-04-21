---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Erfahren Sie, wie Sie einen "Kopier- und Aktualisierungsausdruck" schreiben, der einen vorhandenen Datensatz oder anonymen Datensatz kopiert, bestimmte Felder aktualisiert und den aktualisierten oder anonymen Datensatz zurückgibt.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739287"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="34d37-103">Kopieren und Aktualisieren von Datensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="34d37-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="34d37-104">Ein *Kopier- und Aktualisierungsdatensatzausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert, angegebene Felder aktualisiert und den aktualisierten Datensatz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="34d37-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="34d37-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="34d37-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="34d37-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34d37-106">Remarks</span></span>

<span data-ttu-id="34d37-107">Datensätze und anonyme Datensätze sind standardmäßig unveränderlich, sodass es nicht möglich ist, einen vorhandenen Datensatz zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="34d37-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="34d37-108">Um einen aktualisierten Datensatz zu erstellen, müssten alle Felder eines Datensatzes erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="34d37-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="34d37-109">Um diese Aufgabe zu vereinfachen, kann ein *Kopier- und Aktualisierungsausdruck* verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34d37-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="34d37-110">Dieser Ausdruck nimmt einen vorhandenen Datensatz an, erstellt einen neuen Datensatz desselben Typs mithilfe bestimmter Felder aus dem Ausdruck und des fehlenden Felds, das durch den Ausdruck angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="34d37-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="34d37-111">Dies kann nützlich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="34d37-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="34d37-112">Nehmen Sie zum Beispiel einen neu erstellten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="34d37-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="34d37-113">Um nur zwei Felder in diesem Datensatz zu aktualisieren, können Sie den *Ausdruck "Kopier- und Aktualisierungsdatensatz"* verwenden:</span><span class="sxs-lookup"><span data-stu-id="34d37-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="34d37-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34d37-114">See also</span></span>

- [<span data-ttu-id="34d37-115">Datensätze</span><span class="sxs-lookup"><span data-stu-id="34d37-115">Records</span></span>](records.md)
- [<span data-ttu-id="34d37-116">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="34d37-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="34d37-117">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="34d37-117">F# Language Reference</span></span>](index.md)
