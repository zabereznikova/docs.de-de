---
title: Weitere Steuerungsstrukturen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a>Weitere Steuerungsstrukturen (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bietet Steuerungsstrukturen, mit denen Sie eine Ressource freigeben oder Reduzieren der Anzahl der müssen Sie einen Objektverweis zu wiederholen.  
  
## <a name="usingend-using-construction"></a>Verwenden von... Beenden Sie die Konstruktion verwenden  
 Die `Using...End Using` -Konstruktion erstellt einen Anweisungsblock, anhand derer Sie stellen, eine Ressource, z. B. eine SQL-Verbindung verwenden. Sie können auch die Ressource mit dem Abrufen der `Using` Anweisung. Wenn Sie beenden die `Using` Block [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwirft automatisch der Ressource, sodass sie von anderem Code zu verwenden ist. Die Ressource muss es sich um lokale und verwerfbarer sein. Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Mit... Mit der Konstruktion enden  
 Die `With...End With` Konstruktion können Sie einen Objektverweis einmal angegeben werden, und führen Sie dann eine Reihe von Anweisungen, die die Member zugreifen. Dies kann Ihren Code vereinfachen und Leistung verbessern, da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] muss nicht in der Referenz für jede Anweisung wiederherstellen können, die darauf zugreift. Weitere Informationen finden Sie unter [mit... With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [With...End With-Anweisung](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
