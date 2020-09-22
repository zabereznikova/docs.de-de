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
ms.openlocfilehash: 2f415e70e6ffb5295d49c919383462b9f726f88a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867662"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)

Gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen soll, unabhängig vom Namen der externen Prozedur, die deklariert wird.  
  
 Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen. Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz. Die [Declare-Anweisung](../statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Der `charsetmodifier` Teil in der- `Declare` Anweisung liefert die Zeichensatz Informationen, um Zeichen folgen während eines Aufrufens der externen Prozedur zu Mars Hallen. Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht. Der `Unicode` -Modifizierer gibt an, dass Visual Basic alle Zeichen folgen in Unicode-Werte Mars Hallen und die Prozedur suchen soll, ohne den Namen während der Suche zu ändern.  
  
 Wenn kein zeichensetmodifizierer angegeben wird, `Ansi` ist der Standardwert.  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `Unicode` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  

 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Toleranz](ansi.md)
- [Auto](auto.md)
- [Schlüsselwörter](../keywords/index.md)
