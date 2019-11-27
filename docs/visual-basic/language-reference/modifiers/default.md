---
title: Standard
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
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351582"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifiziert eine Eigenschaft als Standard Eigenschaft ihrer Klasse, Struktur oder Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Eine Klasse, Struktur oder Schnittstelle kann höchstens eine ihrer Eigenschaften als *Standard Eigenschaft*angeben, vorausgesetzt, dass die Eigenschaft mindestens einen Parameter annimmt. Wenn Code einen Verweis auf eine Klasse oder Struktur erstellt, ohne einen Member anzugeben, löst Visual Basic diesen Verweis auf die Standard Eigenschaft auf.  
  
 Standardeigenschaften können zu einer geringfügigen Reduzierung der Quell Code Zeichen führen, aber Sie können den Code schwieriger lesbar machen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, kann er, wenn er einen Verweis auf den Klassen-oder Struktur Namen erstellt, nicht sicher sein, ob dieser Verweis auf die Klasse oder Struktur selbst oder eine Standard Eigenschaft zugreift. Dies kann zu Compilerfehlern oder geringfügigen Lauf Zeit Logik-Fehlern führen.  
  
 Sie können die Wahrscheinlichkeit von Fehlern bei Standardeigenschaften verringern, indem Sie immer die [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf `On`festzulegen.  
  
 Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code zu verwenden, müssen Sie feststellen, ob Sie über eine Default-Eigenschaft verfügt. wenn dies der Fall ist, müssen Sie den Namen angeben.  
  
 Aufgrund dieser Nachteile sollten Sie das Definieren von Standardeigenschaften in Erwägung gezogen. Zur besseren Lesbarkeit des Codes sollten Sie auch immer eine explizite Verweis auf alle Eigenschaften in Erwägung ziehen. Dies gilt auch für Standardeigenschaften.  
  
 Der `Default` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
