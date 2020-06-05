---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 67792e52c21555bef46548e9ab0a6ebd32061071
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373199"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Gibt an, dass Visual Basic alle Zeichen folgen in American National Standards Institute (ANSI)-Werte Mars Hallen soll, unabhängig vom Namen der zu deklarier enden externen Prozedur.  
  
 Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen. Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz. Die [Declare-Anweisung](../statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Der `charsetmodifier` Teil in der- `Declare` Anweisung liefert die Zeichensatz Informationen für das Mars Hallen von Zeichen folgen während eines Aufrufens der externen Prozedur. Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht. Der `Ansi` -Modifizierer gibt an, dass Visual Basic alle Zeichen folgen in ANSI-Werte Mars Hallen und die Prozedur suchen soll, ohne den Namen während der Suche zu ändern.  
  
 Wenn kein zeichensetmodifizierer angegeben wird, `Ansi` ist der Standardwert.  
  
## <a name="remarks"></a>Bemerkungen  
 Der- `Ansi` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  
 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Auto](auto.md)
- [Unicode-](unicode.md)
- [Schlüsselwörter](../keywords/index.md)
