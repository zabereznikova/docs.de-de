---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: b3c9452f8d144fb18ea3efcb35b85caed80e8692
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819345"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Gibt an, dass es sich bei Visual Basic alle Zeichenfolgen in Unicode-Werten, unabhängig vom Namen des deklarierten der externen Prozedur marshallen soll.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur richtig aufrufen. Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Zeichen zum Marshallen von Zeichenfolgen bei einem Aufruf der externen Prozedur Informationen. Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Unicode` %(Dateiname) gibt an, dass Visual Basic alle Zeichenfolgen in Unicode-Werte marshallen und die Prozedur suchen soll, ohne seinen Namen bei der Suche zu ändern.  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Unicode` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Hinweise für Entwickler intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
