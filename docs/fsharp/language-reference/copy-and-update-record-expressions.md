---
title: "Kopieren und Update der Datensatz Ausdrücke (f#)"
description: "Informationen Sie zum Schreiben 'kopieren und Update Datensatz Ausdruck', der einen vorhandenen Datensatz, Updates kopiert Felder angegeben und den aktualisierten Datensatz zurückgegeben."
keywords: Visual F#, F#, funktionale Programmierung
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="1ba5f-104">Kopieren und Aktualisieren von Datensatzausdrücken</span><span class="sxs-lookup"><span data-stu-id="1ba5f-104">Copy and Update Record Expressions</span></span>

<span data-ttu-id="1ba5f-105">Ein *kopieren und update der Datensatz Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt die aktualisierte Datensatz zurück.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-105">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="1ba5f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ba5f-106">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="1ba5f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ba5f-107">Remarks</span></span>
<span data-ttu-id="1ba5f-108">Datensätze sind unveränderlich ist, wird standardmäßig, sodass es kein Update einen vorhandenen Datensatz möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-108">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="1ba5f-109">Um eine aktualisierte Datensatz aller Felder eines Datensatzes erstellen müssten erneut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-109">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="1ba5f-110">Um diese Aufgabe zu vereinfachen ein *kopieren und update der Datensatz Ausdruck* kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-110">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="1ba5f-111">Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue desselben Typs mithilfe des angegebenen Felder aus dem Ausdruck und das fehlende Feld mit dem angegebenen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-111">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="1ba5f-112">Dies kann nützlich sein, wenn Sie zum Kopieren eines vorhandenen Datensatzes und möglicherweise einige der Werte der Felder ändern.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-112">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="1ba5f-113">Nehmen Sie z. B. einen neu erstellten Datensatz.</span><span class="sxs-lookup"><span data-stu-id="1ba5f-113">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="1ba5f-114">Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und update der Datensatz Ausdruck* wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1ba5f-114">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="1ba5f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ba5f-115">See Also</span></span>
[<span data-ttu-id="1ba5f-116">Datensätze</span><span class="sxs-lookup"><span data-stu-id="1ba5f-116">Records</span></span>](records.md)

[<span data-ttu-id="1ba5f-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="1ba5f-117">F# Language Reference</span></span>](index.md)
