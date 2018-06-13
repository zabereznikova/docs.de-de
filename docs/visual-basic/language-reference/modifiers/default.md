---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 555e15110c7af501de05d1f395a72ca4b7800054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595140"
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
