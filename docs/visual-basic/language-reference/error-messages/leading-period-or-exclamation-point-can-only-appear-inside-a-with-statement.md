---
title: Führende &#39;. &#39; oder &#39;! &#39; darf nur innerhalb einer &#39;mit&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625951"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Führende &#39;. &#39; oder &#39;! &#39; darf nur innerhalb einer &#39;mit&#39; Anweisung
Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht innerhalb einer `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite. Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element, das den Member enthält. Dadurch muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` -Block mit den Memberzugriff.  
  
 **Fehler-ID:** BC30157  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Sicherstellen, dass die `With` -Block korrekt formatiert.  
  
2.  Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element, das den Member enthält.  
  
## <a name="see-also"></a>Siehe auch
- [Sonderzeichen in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
