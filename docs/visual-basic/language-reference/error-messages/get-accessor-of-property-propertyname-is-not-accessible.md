---
title: '&#39; Get &#39; Accessor der Eigenschaft der &#39; &lt;Propertyname&gt;&#39; kann nicht zugegriffen werden'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords: BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 167e040570af1fc78ce48f5e930e54981ba909ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Get &#39; Accessor der Eigenschaft der &#39; &lt;Propertyname&gt;&#39; kann nicht zugegriffen werden
Eine Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn er keinen Zugriff auf der Eigenschaft hat `Get` Prozedur.  
  
 Wenn die [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md) RuntimeCompatibility mit einer restriktiveren Zugriffsebene als seine [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md), beim Lesen des Eigenschaftswerts kann fehlschlagen, in den folgenden Fällen:  
  
-   Die `Get` Anweisung RuntimeCompatibility [Private](../../../visual-basic/language-reference/modifiers/private.md) und der aufrufende Code außerhalb der Klasse oder Struktur, die in der die Eigenschaft definiert ist.  
  
-   Die `Get` Anweisung RuntimeCompatibility [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) und der aufrufende Code befindet sich nicht in der Klasse oder Struktur, die in der die Eigenschaft definiert ist, noch in einer abgeleiteten Klasse.  
  
-   Die `Get` Anweisung RuntimeCompatibility ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) und der aufrufende Code ist nicht in der gleichen Assembly, in dem die Eigenschaft definiert wird.  
  
 **Fehler-ID:** BC31103  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie die Kontrolle des Quellcodes die-Eigenschaft definiert haben, sollten Sie deklarieren die `Get` Prozedur mit die gleiche Zugriffsebene wie die Eigenschaft selbst.  
  
-   Wenn Sie keine Kontrolle über den Quellcode der-Eigenschaft definiert wird, oder Sie einschränken, müssen die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst, versuchen Sie es so verschieben Sie die Anweisung, die Wert der Eigenschaft auf einen Codebereich liest, die besseren Zugriff auf die Diese Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
