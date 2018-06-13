---
title: Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einem &#39;mit&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 7802b8e0aaf3dff83d5bfbe11f0b8bb1b5bb46cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589446"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einem &#39;mit&#39; Anweisung
Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht in einem `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite. Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element mit dem Element angeben. Dies muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` Block, der den Memberzugriffsoperator enthält.  
  
 **Fehler-ID:** BC30157  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Sicherstellen, dass die `With` -Block ordnungsgemäß formatiert.  
  
2.  Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element mit dem Element.  
  
## <a name="see-also"></a>Siehe auch  
 [Sonderzeichen in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
