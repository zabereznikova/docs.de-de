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
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800931"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Gibt eine Eigenschaft als Standardeigenschaft von der Klasse, Struktur oder Schnittstelle an.  
  
## <a name="remarks"></a>Hinweise  
 Eine Klasse, Struktur oder Schnittstelle kann höchstens eine der Eigenschaften als Festlegen der *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter akzeptiert. Wenn der Code einen Verweis auf eine Klasse oder Struktur ist ein Mitglied angegeben, löst Visual Basic dieser Verweis auf die Standardeigenschaft.  
  
 Standardeigenschaften können dazu führen, eine kleine Reduzierung in Code-Zeichen, aber leisten können Ihren Code schwieriger zu lesen. Wenn der aufrufende Code nicht vertraut sind, mit der Klasse oder Struktur ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur ist es bestimmte nicht möglich, ob der Verweis der Klasse oder Struktur selbst oder an eine Standardeigenschaft greift auf. Dies kann zu Compilerfehlern oder geringfügige Laufzeitlogik-Fehler führen.  
  
 Sie können etwas reduziert die Wahrscheinlichkeit Eigenschaftenfehler standardmäßig immer mit der [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) Festlegen der Compiler die typüberprüfung zu `On`.  
  
 Wenn Sie beabsichtigen, mit einer vordefinierten Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist wie der Name.  
  
 Wegen der genannten Nachteile sollten Sie keine Standardeigenschaften definieren. Sie sollten für die Lesbarkeit des Codes berücksichtigen Sie auch immer explizit verweisen, die allen Eigenschaften, auch die Standardeigenschaften.  
  
 Die `Default` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
