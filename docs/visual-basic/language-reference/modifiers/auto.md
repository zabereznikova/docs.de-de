---
title: Auto
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 799a7320b701384dc5f4b4b46fef8544f6b15b02
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875516"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)

Gibt an, dass Visual Basic Zeichen folgen gemäß .NET Framework Regeln Mars Hallen soll, basierend auf dem externen Namen der zu deklarierten externen Prozedur.  
  
 Wenn Sie eine Prozedur aufrufen, die außerhalb des Projekts definiert ist, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen. Diese Informationen umfassen den Speicherort der Prozedur, deren Identifizierung, die Aufruf Sequenz und den Rückgabetyp sowie den verwendeten Zeichen folgen Zeichensatz. Die [Declare-Anweisung](../statements/declare-statement.md) erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.  
  
 Der `charsetmodifier` Teil in der- `Declare` Anweisung liefert die Zeichensatz Informationen für das Mars Hallen von Zeichen folgen während eines Aufrufens der externen Prozedur. Es wirkt sich auch darauf aus, wie Visual Basic die externe Datei nach dem Namen der externen Prozedur durchsucht. Der- `Auto` Modifizierer gibt an, dass Visual Basic Zeichen folgen gemäß .NET Framework Regeln Mars Hallen und den Basis Zeichensatz der Laufzeitplattform bestimmen und ggf. den Namen der externen Prozedur ändern soll, wenn bei der ersten Suche ein Fehler auftritt. Weitere Informationen finden Sie unter "Zeichensätze" in der [Declare-Anweisung](../statements/declare-statement.md).  
  
 Wenn kein zeichensetmodifizierer angegeben wird, `Ansi` ist der Standardwert.  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `Auto` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  

 Dieses Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Toleranz](ansi.md)
- [Unicode](unicode.md)
- [Schlüsselwörter](../keywords/index.md)
