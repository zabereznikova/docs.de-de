---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa5724eb9123b2776c3a579e4244c55b3129816b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Gibt an, dass Visual Basic alle Zeichenfolgen in American National Standards Institute (ANSI)-Werte unabhängig von den Namen der die deklarierte externe Prozedur marshallen soll.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen zum ordnungsgemäßen Aufrufen der Prozedur benötigt. Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` teilweise in die `Declare` Anweisung liefert die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf an die externe Prozedur Zeichen. Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Ansi` Modifizierer gibt an, dass Visual Basic alle Zeichenfolgen in ANSI-Werte marshallen und die Prozedur nachschlagen soll, ohne den Namen ändern, während der Suche.  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Ansi` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwicklerhinweise für intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
