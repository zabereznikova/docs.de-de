---
title: Das Array ist fixiert oder vorübergehend gesperrt
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350791"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
Dieser Fehler kann folgende Ursachen haben:  
  
- Mithilfe `ReDim` können Sie die Anzahl von Elementen eines Arrays mit fester Größe ändern.  
  
- Neudimensionierung eines dynamischen Arrays auf Modulebene, in dem ein Element als Argument an eine Prozedur weitergegeben wurde. Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass der Speicherplatz für den Verweis Parameter innerhalb der Prozedur aufgehoben wird.  
  
- Es wird versucht, einer `Variant` Variablen, die ein Array enthält, einen Wert zuzuweisen, aber der `Variant` ist zurzeit gesperrt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Legen Sie das ursprüngliche Array dynamisch und nicht fest, indem Sie es mit `ReDim` deklarieren (wenn das Array innerhalb einer Prozedur deklariert ist), oder indem Sie es deklarieren, ohne die Anzahl der Elemente anzugeben (wenn das Array auf Modulebene deklariert ist).  
  
2. Stellen Sie fest, ob das Element wirklich übergeben werden muss, da es in allen Prozeduren im Modul sichtbar ist.  
  
3. Bestimmen Sie, was das `Variant` sperrt, und beheben Sie es.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
