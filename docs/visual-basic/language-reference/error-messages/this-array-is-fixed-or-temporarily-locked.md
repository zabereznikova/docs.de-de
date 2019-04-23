---
title: Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337967"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Mithilfe von `ReDim` so ändern Sie die Anzahl der Elemente eines Arrays fester Größe.  
  
-   Neudimensionierung ein auf Modulebene dynamisches Array, in dem ein Element an eine Prozedur als Argument übergeben wurde. Wenn ein Element übergeben wird, ist das Array gesperrt, um zu verhindern, dass Freigeben von Speicher für der Verweisparameter, in der Prozedur.  
  
-   Es wird versucht, einen Wert zuweisen einer `Variant` Variable, die ein Array ist, enthält aber die `Variant` ist zurzeit gesperrt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie das ursprüngliche Array dynamisch und nicht als deklarieren Sie es mit festen `ReDim` (wenn das Array in einer Prozedur deklariert wird), oder deklarieren es ohne Angabe der Anzahl der Elemente, (wenn das Array auf der Modulebene deklariert wird.  
  
2. Bestimmen Sie, ob Sie wirklich benötigen, um das Element, zu übergeben, da es in alle Verfahren im Modul angezeigt wird.  
  
3. Bestimmen, was verhindert die `Variant` und beheben sie das Problem.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
