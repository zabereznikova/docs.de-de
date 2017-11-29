---
title: "Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic)."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Mithilfe von `ReDim` so ändern Sie die Anzahl der Elemente eines Arrays mit fester Größe.  
  
-   Neudimensionierung auf Modulebene dynamisches Array, in dem ein Element als Argument an eine Prozedur wurde übergeben. Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass Freigeben von Speicher für die Verweisparameter innerhalb der Prozedur.  
  
-   Bei dem Versuch, einen Wert zuzuweisen eine `Variant` Variable, die ein Array ist, enthält aber die `Variant` ist derzeit gesperrt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie das ursprüngliche Array dynamische statt mit festen `ReDim` (wenn das Array in einer Prozedur deklariert ist), oder deklarieren Sie es ohne Angabe der Anzahl von Elementen (wenn das Array auf Modulebene deklariert wird.  
  
2.  Bestimmen Sie, ob Sie tatsächlich das Element zu übergeben, da es in allen Prozeduren im Modul angezeigt wird.  
  
3.  Bestimmen, welche Sperren ist der `Variant` und beheben sie das Problem.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
