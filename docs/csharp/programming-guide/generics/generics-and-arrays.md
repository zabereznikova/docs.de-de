---
title: Generika und Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 6cb205d90d4b6de329a179c5969e2d3b543bfb35
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528499"
---
# <a name="generics-and-arrays-c-programming-guide"></a>Generika und Arrays (C#-Programmierhandbuch)
In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch. So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können. Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich. Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen. Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.  
  
 Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Generika](../../../csharp/programming-guide/generics/index.md)  
- [Arrays](../../../csharp/programming-guide/arrays/index.md)  
- [Generika](~/docs/standard/generics/index.md)
