---
title: Erase-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 33d88b5ce71ceab8d4b4b59d356c53a804c360be
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873287"
---
# <a name="erase-statement-visual-basic"></a>Erase-Anweisung (Visual Basic)

Wird zum Freigeben von Array Variablen und zum Freigeben des für ihre Elemente verwendeten Speichers verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Bestandteile  

 `arraylist`  
 Erforderlich. Liste der zu löschenden Array Variablen. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
## <a name="remarks"></a>Bemerkungen  

 Die- `Erase` Anweisung kann nur auf Prozedur Ebene angezeigt werden. Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur freigeben können, jedoch nicht auf Klassen-oder Modulebene.  
  
 Die- `Erase` Anweisung entspricht der Zuweisung `Nothing` zu jeder Array Variablen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die `Erase` -Anweisung verwendet, um zwei Arrays zu löschen und Ihren Arbeitsspeicher (1000 bzw. 100 Speicherelemente) freizugeben. Die- `ReDim` Anweisung weist dann dem dreidimensionalen Array eine neue Array Instanz zu.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schweigen](../nothing.md)
- [ReDim-Anweisung](redim-statement.md)
