---
title: Generics und Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: a8fad38fac07b9e8d51529d3ab7070328a333dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75703012"
---
# <a name="generics-and-arrays-c-programming-guide"></a>Generics und Arrays (C#-Programmierhandbuch)
In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch. So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können. Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich. Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen. Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.  
  
 Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Generics](./index.md)
- [Arrays](../arrays/index.md)
- [Generics](../../../standard/generics/index.md)
