---
title: Auto (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e32c4c910567829a4f5c59b48020db4dfbbeb7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Gibt an, dass Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln, die basierend auf den externen Namen der externen Prozedur, die deklariert wird.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie zum ordnungsgemäßen Aufrufen der Prozedur benötigen. Diese Informationen umfassen, auf dem sich die Prozedur befindet, wie festgestellt wird, werden der Aufrufsequenz und Rückgabetyp und die Zeichenfolge verwendeten Zeichensatz. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` teilweise in die `Declare` Anweisung liefert die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf an die externe Prozedur Zeichen. Er wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Auto` Modifizierer gibt an, dass Visual Basic Marshallen von Zeichenfolgen .NET Framework-Regeln entsprechend, und, dass die Basis Zeichensatz der Plattform zur Laufzeit und möglicherweise bestimmt werden soll, den Namen der externen Prozedur, ändern Wenn der anfänglichen Suche ein Fehler auftritt. Weitere Informationen finden Sie unter "Zeichensätze" in [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Auto` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwicklerhinweise für intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
