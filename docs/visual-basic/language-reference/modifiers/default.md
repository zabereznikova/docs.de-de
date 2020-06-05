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
ms.openlocfilehash: 0c2808795d6fcbad7892369fd7f460ebf0406093
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372971"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifiziert eine Eigenschaft als Standard Eigenschaft ihrer Klasse, Struktur oder Schnittstelle.  
  
## <a name="remarks"></a>Bemerkungen  
 Eine Klasse, Struktur oder Schnittstelle kann höchstens eine ihrer Eigenschaften als *Standard Eigenschaft*angeben, vorausgesetzt, dass die Eigenschaft mindestens einen Parameter annimmt. Wenn Code einen Verweis auf eine Klasse oder Struktur erstellt, ohne einen Member anzugeben, löst Visual Basic diesen Verweis auf die Standard Eigenschaft auf.  
  
 Standardeigenschaften können zu einer geringfügigen Reduzierung der Quell Code Zeichen führen, aber Sie können den Code schwieriger lesbar machen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, kann er, wenn er einen Verweis auf den Klassen-oder Struktur Namen erstellt, nicht sicher sein, ob dieser Verweis auf die Klasse oder Struktur selbst oder eine Standard Eigenschaft zugreift. Dies kann zu Compilerfehlern oder geringfügigen Lauf Zeit Logik-Fehlern führen.  
  
 Sie können die Wahrscheinlichkeit von Fehlern bei Standardeigenschaften verringern, indem Sie immer die [Option Strict-Anweisung](../statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf festzulegen `On` .  
  
 Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code zu verwenden, müssen Sie feststellen, ob Sie über eine Default-Eigenschaft verfügt. wenn dies der Fall ist, müssen Sie den Namen angeben.  
  
 Aufgrund dieser Nachteile sollten Sie das Definieren von Standardeigenschaften in Erwägung gezogen. Zur besseren Lesbarkeit des Codes sollten Sie auch immer eine explizite Verweis auf alle Eigenschaften in Erwägung ziehen. Dies gilt auch für Standardeigenschaften.  
  
 Der- `Default` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property Statement](../statements/property-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Schlüsselwörter](../keywords/index.md)
