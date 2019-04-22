---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843837"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Gibt an, dass es sich bei Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln, die basierend auf den externen Namen der externen Prozedur deklariert wird.  
  
 Wenn Sie eine Prozedur, die außerhalb des Projekts definiert aufrufen, Visual Basic-Compiler keinen Zugriff auf die Informationen, die sie benötigen, um die Prozedur aufrufen, ordnungsgemäß. Diese Informationen umfassen, in dem die Prozedur befindet, wie dieses ermittelt wird, die Aufrufsequenz und Rückgabetyp und die Zeichenfolge festgelegt wird. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Die `charsetmodifier` -Teil in die `Declare` -Anweisung gibt die Informationen für das Marshalling von Zeichenfolgen bei einem Aufruf der externen Prozedur Zeichen. Es wirkt sich auch, wie Visual Basic die externe Datei für den externen Prozedurnamen durchsucht. Die `Auto` %(Dateiname) gibt an, dass Visual Basic Zeichenfolgen gemäß der .NET Framework-Regeln marshallen, und, dass die Basis Zeichensatz der Laufzeit-Plattform und möglicherweise bestimmt werden soll den externen Prozedurnamen ändern, wenn es sich bei der anfänglichen Suche ein Fehler auftritt. Weitere Informationen finden Sie unter "Zeichensatz" in [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Wenn kein Modifizierer angegeben ist, `Ansi` ist die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `Auto` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Hinweise für Entwickler intelligente Geräte  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
