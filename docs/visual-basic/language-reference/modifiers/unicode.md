---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 042908b8427de2de0de96bbb32df7be018bb915c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte unabhängig von den Namen der die deklarierte externe Prozedur marshallen soll.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur ordnungsgemäß aufrufen. Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` teilweise in die `Declare` -Anweisung gibt die Zeichen zum Marshallen von Zeichenfolgen während eines Aufrufs an die externe Prozedur Informationen. Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Unicode` Modifizierer gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte marshallen und die Prozedur nachschlagen soll, ohne den Namen ändern, während der Suche.  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Unicode` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwicklerhinweise für intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
