---
title: Verzweigte Arrays – C#-Programmierhandbuch
description: Ein Jagged Array in C# ist ein Array, dessen Elemente Arrays verschiedener Größe sind. Hier erfahren Sie, wie Sie Jagged Arrays deklarieren, initialisieren und auf sie zugreifen.
ms.date: 12/18/2020
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 6d4fb939fb6594c7644a80eb688ea852ddf8a5c5
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737280"
---
# <a name="jagged-arrays-c-programming-guide"></a>Verzweigte Arrays (C#-Programmierhandbuch)

Ein Jagged Array ist ein Array, dessen Elemente Arrays möglicherweise verschiedener Größe sind. Ein verzweigtes Array wird auch „Array aus Arrays“ genannt. Die folgenden Beispiele zeigen, wie Sie verzweigte Arrays deklarieren, initialisieren und auf sie zugreifen können.

 Die folgende Deklaration veranschaulicht ein eindimensionales Array mit drei Elementen, von denen jedes wiederum ein eindimensionales Array aus ganzen Zahlen darstellt:

 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]

 Vor der Verwendung von `jaggedArray` müssen seine Elemente initialisiert werden. Sie können die Elemente folgendermaßen initialisieren:

 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]

 Jedes Element ist ein eindimensionales Array aus ganzen Zahlen. Das erste Element ist ein Array aus 5 ganzen Zahlen, das zweite aus 4 und das dritte aus 2.

 Sie können auch Initialisierer verwenden, um die Arrayelemente mit Werten zu füllen. In diesem Fall wird die Arraygröße nicht benötigt. Zum Beispiel:

 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]

 Sie können das Array auch nach der Deklaration folgendermaßen initialisieren:

 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]

 Sie können folgende Kurzformen verwenden. Beachten Sie, dass der Operator `new` bei der Initialisierung der Elemente nicht ausgelassen werden kann, da es für die Elemente keine Standardinitialisierung gibt:

 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]

 Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.

 In den folgenden Beispielen wird veranschaulicht, wie Sie auf einzelne Arrayelemente zugreifen können:

 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]

 Es ist möglich, Jagged Arrays und mehrdimensionale Arrays zu mischen. Das folgende Beispiel zeigt die Deklaration und Initialisierung eines eindimensionalen verzweigten Arrays, das drei zweidimensionale Arrayelemente unterschiedlicher Größe enthält. Weitere Informationen finden Sie unter [Mehrdimensionale Arrays](./multidimensional-arrays.md).

 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]

 Im folgenden Beispiel wird dargestellt, wie Sie auf einzelne Elemente zugreifen können. Der Wert des Elements `[1,0]` des ersten Arrays (Wert `5`) wird angezeigt:

 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]

 Die Methode `Length` gibt die Anzahl der Arrays zurück, die im verzweigten Array enthalten sind. Wenn Sie beispielsweise das vorherige Array deklariert haben, dann gibt die folgende Zeile:

 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]

 den Wert 3 zurück.

## <a name="example"></a>Beispiel

 In diesem Beispiel wird ein Array erstellt, dessen Elemente wiederum selbst Arrays sind. Jedes Arrayelement hat eine unterschiedliche Größe.

 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Array>
- [C#-Programmierhandbuch](../index.md)
- [Arrays](./index.md)
- [Eindimensionale Arrays](./single-dimensional-arrays.md)
- [Mehrdimensionale Arrays](./multidimensional-arrays.md)
