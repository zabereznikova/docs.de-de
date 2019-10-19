---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583385"
---
# <a name="erase-statement-visual-basic"></a>Erase-Anweisung (Visual Basic)
Wird zum Freigeben von Array Variablen und zum Freigeben des für ihre Elemente verwendeten Speichers verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Teile  
 `arraylist`  
 Erforderlich. Liste der zu löschenden Array Variablen. Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
## <a name="remarks"></a>Hinweise  
 Die `Erase`-Anweisung kann nur auf Prozedur Ebene angezeigt werden. Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur freigeben können, jedoch nicht auf Klassen-oder Modulebene.  
  
 Die `Erase`-Anweisung entspricht der Zuweisung von `Nothing` zu jeder Array Variablen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die `Erase`-Anweisung verwendet, um zwei Arrays zu löschen und Ihren Arbeitsspeicher (1000 bzw. 100 Speicherelemente) freizugeben. Die `ReDim`-Anweisung weist dann dem dreidimensionalen Array eine neue Array Instanz zu.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
