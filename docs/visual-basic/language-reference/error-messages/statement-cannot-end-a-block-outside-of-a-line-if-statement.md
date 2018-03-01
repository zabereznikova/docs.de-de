---
title: "Einen Block außerhalb einer Zeile &#39; kann nicht abgeschlossen werden. wenn &#39; Anweisung"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Einen Block außerhalb einer Zeile &#39; kann nicht abgeschlossen werden. wenn &#39; Anweisung
Eine einzeilige `If` -Anweisung enthält mehrere Anweisungen, die getrennt durch Doppelpunkte (:)), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`. Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.  
  
 **Fehler-ID:** BC32005  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verschieben Sie die einzeilige `If` Anweisung außerhalb der Kontrollblock enthält, die die `End If` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
