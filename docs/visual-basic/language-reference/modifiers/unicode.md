---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: c4286ed9e9d5fd768ae29b7050b3d1505ccca9dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344224"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen soll, unabhängig vom Namen der externen Prozedur, die deklariert wird.  
  
 Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen. Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz. Die [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Der `charsetmodifier` Teil in der `Declare`-Anweisung liefert die Zeichensatz Informationen, um Zeichen folgen während eines Aufrufens der externen Prozedur zu Mars Hallen. Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht. Der `Unicode` Modifizierer gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen und die Prozedur suchen soll, ohne den Namen während der Suche zu ändern.  
  
 Wenn kein zeichensetmodifizierer angegeben ist, ist `Ansi` der Standardwert.  
  
## <a name="remarks"></a>Hinweise  
 Der `Unicode` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
