---
title: Erstellen einer geschachtelten Gruppe (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie eine geschachtelten Gruppe in einem LINQ-Abfrageausdruck in C# erstellen.
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 82b07c303215200fa974ce614a2d5a77882dcf4c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509967"
---
# <a name="create-a-nested-group"></a>Erstellen einer geschachtelten Gruppe

Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden. Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.

## <a name="example"></a>Beispiel

> [!NOTE]
> Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)
