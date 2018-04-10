---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Gibt eine Eigenschaft als Standardeigenschaft von der Klasse, Struktur oder Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Eine Klasse, Struktur oder Schnittstelle kann höchstens eine seiner Eigenschaften als Festlegen der *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter übernimmt. Wenn der Code einen Verweis auf eine Klasse oder Struktur vornimmt, ohne dass ein Element, löst Visual Basic, Verweis auf die Standardeigenschaft.  
  
 Standardeigenschaften können dazu führen, eine kleine Verkleinerung an Code Quellzeichen können, sie jedoch Code schwieriger zu lesen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur enthält kann nicht bestimmte darauf, ob der Verweis der Klasse oder Struktur selbst oder eine Standardeigenschaft greift auf. Dies kann zu Compilerfehlern oder geringfügige Logikfehler zur Laufzeit führen.  
  
 Sie können das Risiko von Fehlern der Standard-Eigenschaft etwas reduzieren, indem immer mithilfe der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp das Einchecken festlegen `On`.  
  
 Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist was seinen Namen aus.  
  
 Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren. Für die Lesbarkeit des Codes sollten Sie auch sollten Sie immer alle Eigenschaften explizit auf, auch die Standardeigenschaften.  
  
 Die `Default` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
