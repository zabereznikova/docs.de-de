---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a>Erase-Anweisung (Visual Basic)
Zum Arrayvariablen freigeben und Aufheben der Zuordnung für ihre Elemente verwendeten Arbeitsspeichers.  
  
## <a name="syntax"></a>Syntax  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Teile  
 `arraylist`  
 Erforderlich. Liste der Arrayvariablen gelöscht werden soll. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Erase` Anweisung kann nur auf Prozedurebene angezeigt werden. Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur, aber nicht auf Klassen-oder Modulebene freigeben können.  
  
 Die `Erase` Anweisung ist äquivalent zum Zuweisen von `Nothing` jedes Array-Variable.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Erase` Anweisung zum Löschen von zwei Arrays und Freigeben von Speicher (1000 und 100 Speicherelemente bzw.). Die `ReDim` Anweisung dann weist eine neue Arrayinstanz auf das dreidimensionale Array.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
