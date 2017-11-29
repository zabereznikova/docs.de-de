---
title: "Ausführen einer Unterabfrage für eine Gruppierungsoperation"
description: "So führen Sie eine Unterabfrage für eine Gruppierungsoperation aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: f638b8a679a15891d04e02f1597d6bf7934a9e74
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Ausführen einer Unterabfrage für eine Gruppierungsoperation

In diesem Thema werden zwei verschiedene Möglichkeiten gezeigt, um eine Abfrage zu erstellen, die Quelldaten in Gruppen sortiert und anschließend eine Unterabfrage für jede einzelne Gruppe ausführt. Die grundlegende Technik in jedem Beispiel besteht darin, die Quellelemente mithilfe einer *Fortsetzung* namens `newGroup` zu gruppieren und anschließend eine neue Unterabfrage für `newGroup` zu erzeugen. Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wurde. Beachten Sie, dass in diesem speziellen Beispiel die endgültige Ausgabe keine Gruppe ist, sondern eine flache Sequenz von anonymen Typen.  
  
 Weitere Informationen zum Gruppieren finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).  
  
 Weitere Informationen zu Fortsetzungen finden Sie unter [into](../language-reference/keywords/into.md). Im folgenden Beispiel wird eine Datenstruktur im Arbeitsspeicher als Datenquelle verwendet, jedoch gelten für jede Art von LINQ-Datenquelle die gleichen Prinzipien.  
  
## <a name="example"></a>Beispiel 

 > [!NOTE]
 > Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)
