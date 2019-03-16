---
title: Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039427"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
Ein zyklischer Vorgang ist fehlgeschlagen. Ein zyklischer Vorgang wird zyklisch ausgeführt und kann daher nicht abgeschlossen werden. Beispielsweise könnte Objekt A versuchen, von Objekt B zu erben, das wiederum versucht, von Objekt A zu erben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn geerbt wird, müssen Sie sicherstellen, dass keine zyklischen Verweise vorhanden sind.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../visual-basic/programming-guide/language-features/error-types.md)
- [Verwenden von Haltepunkten in Visual Studio-debugger](/visualstudio/debugger/using-breakpoints)
