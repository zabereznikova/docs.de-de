---
title: "Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0304f04233151d35c8ee18fe09feac91fbd0879b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)
Sie können `accessor-declarations` dazu verwenden, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld hinzufügen zu müssen, indem Sie stattdessen ein Wörterbuch verwenden, um die Ereignisinstanzen zu speichern. Dies ist jedoch nur nützlich, wenn Sie viele Ereignisse haben, Sie aber davon ausgehen, dass viele der Ereignisse nicht implementiert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)  
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)
