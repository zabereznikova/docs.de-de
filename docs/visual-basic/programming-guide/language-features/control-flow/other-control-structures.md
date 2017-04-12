---
title: Weitere Steuerungsstrukturen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 639571b493037f26951bd8fbf140d7bce3244889
ms.lasthandoff: 03/13/2017

---
# <a name="other-control-structures-visual-basic"></a>Weitere Steuerungsstrukturen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet Steuerungsstrukturen, mit denen Sie eine Ressource freigeben oder Reduzieren der Anzahl der müssen Sie einen Objektverweis zu wiederholen.  
  
## <a name="usingend-using-construction"></a>Verwenden von... End Using-Konstruktion  
 Die `Using...End Using` -Konstruktion erstellt einen Anweisungsblock, in dem Sie vornehmen, einer Ressource, z. B. eine SQL-Verbindung verwenden. Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung. Wenn Sie schließen die `Using` Block [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatisch gibt die Ressource frei, damit er für anderen Code für die Verwendung verfügbar ist. Die Ressource muss es sich um lokale und freigegeben sein. Weitere Informationen finden Sie unter [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Mit... Endet mit der Konstruktion  
 Die `With...End With` Konstruktion können Sie einmal einen Objektverweis angeben und führen Sie dann eine Reihe von Anweisungen, die auf Member zugreifen. Dies kann Ihren Code vereinfachen und Leistung verbessern, da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keinen den Verweis für jede Anweisung, die darauf zugreift, erneut erstellen. Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
