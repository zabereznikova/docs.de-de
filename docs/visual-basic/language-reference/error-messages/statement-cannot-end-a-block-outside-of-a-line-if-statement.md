---
title: Anweisung kann nicht beendet einen Block außerhalb einer Zeile &#39;Wenn&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Anweisung kann nicht beendet einen Block außerhalb einer Zeile &#39;Wenn&#39; Anweisung
Eine einzeilige `If` -Anweisung enthält mehrere Anweisungen, die getrennt durch Doppelpunkte (:)), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`. Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.  
  
 **Fehler-ID:** BC32005  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verschieben Sie die einzeilige `If` Anweisung außerhalb der Kontrollblock enthält, die die `End If` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
