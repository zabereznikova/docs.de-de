---
title: 'Vorgehensweise: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245141"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Vorgehensweise: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)
Sie können `accessor-declarations` dazu verwenden, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld hinzufügen zu müssen, indem Sie stattdessen ein Wörterbuch verwenden, um die Ereignisinstanzen zu speichern. Dies ist jedoch nur nützlich, wenn Sie viele Ereignisse haben, Sie aber davon ausgehen, dass viele der Ereignisse nicht implementiert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Ereignisse](../../../csharp/programming-guide/events/index.md)  
- [Delegaten](../../../csharp/programming-guide/delegates/index.md)
