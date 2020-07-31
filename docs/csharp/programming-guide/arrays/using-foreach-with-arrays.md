---
title: Verwenden von „foreach“ mit Arrays – C#-Programmierhandbuch
description: Die foreach-Anweisung in C# durchläuft die Elemente eines Arrays. Bei eindimensionalen Arrays verarbeitet die foreach-Anweisung Prozesselemente in zunehmender Indexreihenfolge.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474539"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Verwenden von foreach mit Arrays (C#-Programmierhandbuch)

Die Anweisung [foreach](../../language-reference/keywords/foreach-in.md) stellt eine einfache, klare Methode bereit, um die Elemente eines Arrays zu durchlaufen.

Bei eindimensionalen Arrays verarbeitet die Anweisung `foreach` Elemente in aufsteigender Indexreihenfolge, beginnend bei Index 0 und endend bei Index `Length - 1`:

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

Bei mehrdimensionalen Arrays werden Elemente so durchlaufen, dass die Indizes der äußersten rechten Dimension zuerst erhöht werden, dann die der links daneben liegenden Dimension und so weiter, bis die linke Seite erreicht ist:

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

Bei mehrdimensionalen Arrays haben Sie jedoch eine größere Kontrolle über die Reihenfolge bei der Verarbeitung von Arrayelementen, wenn Sie eine geschachtelte [for](../../language-reference/keywords/for.md)-Schleife verwenden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Array>
- [C#-Programmierhandbuch](../index.md)
- [Arrays](index.md)
- [Eindimensionale Arrays](single-dimensional-arrays.md)
- [Mehrdimensionale Arrays](multidimensional-arrays.md)
- [Verzweigte Arrays](jagged-arrays.md)
