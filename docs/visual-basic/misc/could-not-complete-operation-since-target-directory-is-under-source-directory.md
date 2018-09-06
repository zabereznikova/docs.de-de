---
title: Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: b821034731514362a3725c390e02542b536f0a59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890803"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
Ein zyklischer Vorgang ist fehlgeschlagen. Ein zyklischer Vorgang wird zyklisch ausgeführt und kann daher nicht abgeschlossen werden. Beispielsweise könnte Objekt A versuchen, von Objekt B zu erben, das wiederum versucht, von Objekt A zu erben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn geerbt wird, müssen Sie sicherstellen, dass keine zyklischen Verweise vorhanden sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Grundlagen des Debuggens: Haltepunkte](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
