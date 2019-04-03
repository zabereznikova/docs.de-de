---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840405"
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
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
