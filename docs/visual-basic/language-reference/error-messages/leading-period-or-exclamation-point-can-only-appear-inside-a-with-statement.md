---
title: "Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einer &#39; Mit &#39; Anweisung"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Führende &#39;. &#39; oder &#39;! &#39; kann nur verwendet werden, in einer &#39; Mit &#39; Anweisung
Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht in einem `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite. Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element mit dem Element angeben. Dies muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` Block, der den Memberzugriffsoperator enthält.  
  
 **Fehler-ID:** BC30157  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Sicherstellen, dass die `With` -Block ordnungsgemäß formatiert.  
  
2.  Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element mit dem Element.  
  
## <a name="see-also"></a>Siehe auch  
 [Sonderzeichen in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
