---
title: Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 15390fb506fe9bca10f6917f5b26451a5569bece
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322848"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>Vorangestellte "." oder "!" können nur in einer With-Anweisung verwendet werden.
Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht innerhalb einer `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite. Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element, das den Member enthält. Dadurch muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` -Block mit den Memberzugriff.  
  
 **Fehler-ID:** BC30157  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Sicherstellen, dass die `With` -Block korrekt formatiert.  
  
2. Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element, das den Member enthält.  
  
## <a name="see-also"></a>Siehe auch

- [Sonderzeichen in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
