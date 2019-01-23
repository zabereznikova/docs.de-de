---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: cab3da4465b4671d203036c2d9bcd40662dc234a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522439"
---
# <a name="erase-statement-visual-basic"></a>Erase-Anweisung (Visual Basic)
Zum Freigeben von Arrayvariablen und Freigeben des Speicherplatzes, der für ihre Elemente verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Teile  
 `arraylist`  
 Erforderlich. Liste der Arrayvariablen gelöscht werden soll. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Erase` Anweisung kann nur auf Prozedurebene angezeigt werden. Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur, aber nicht auf Klassen-oder Modulebene freigeben können.  
  
 Die `Erase` -Anweisung ist identisch mit der Zuweisung `Nothing` jedes Array-Variable.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Erase` Anweisung, um zwei Arrays gelöscht und deren Speicher freigeben (1000 und 100 Speicherelemente, bzw.). Die `ReDim` Anweisung dann weist eine neue Arrayinstanz, auf das dreidimensionale Array.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
