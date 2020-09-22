---
title: Das Array ist fixiert oder vorübergehend gesperrt
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 05fb8e2ef788920fd200d79a75eec3d7c252b123
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873588"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).

Dieser Fehler kann folgende Ursachen haben:  
  
- Mithilfe `ReDim` von können Sie die Anzahl von Elementen eines Arrays mit fester Größe ändern.  
  
- Neudimensionierung eines dynamischen Arrays auf Modulebene, in dem ein Element als Argument an eine Prozedur weitergegeben wurde. Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass der Speicherplatz für den Verweis Parameter innerhalb der Prozedur aufgehoben wird.  
  
- Es wird versucht, einer `Variant` Variablen, die ein Array enthält, einen Wert zuzuweisen, aber die `Variant` ist zurzeit gesperrt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Legen Sie das ursprüngliche Array dynamisch und nicht fest, indem Sie es mit deklarieren `ReDim` (wenn das Array innerhalb einer Prozedur deklariert ist), oder indem Sie es deklarieren, ohne die Anzahl der Elemente anzugeben (wenn das Array auf Modulebene deklariert ist).  
  
2. Stellen Sie fest, ob das Element wirklich übergeben werden muss, da es in allen Prozeduren im Modul sichtbar ist.  
  
3. Legen Sie fest, was gesperrt ist, `Variant` und beheben Sie es.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../programming-guide/language-features/arrays/index.md)
