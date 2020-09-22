---
title: Ungültige Datensatzlänge.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869263"
---
# <a name="bad-record-length"></a>Ungültige Datensatzlänge.

Zu den möglichen Ursachen für diesen Fehler gehören:  
  
- Die Länge einer Daten Satz Variablen, die in einer-,-oder-Anweisung angegeben ist, unter `FileGet` `FileGetObject` scheidet sich `FilePut` `FilePutObject` von der in der entsprechenden-Anweisung angegebenen Länge `FileOpen` .  
  
- Die-Variable in einer- `FilePut` oder `FilePutObject` -Anweisung ist oder enthält eine Zeichenfolge variabler Länge.  
  
- Die-Variable in einem `FilePut` oder `FilePutObject` ist oder enthält einen- `Variant` Typ.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die Summe der Größen von Variablen fester Länge im benutzerdefinierten Typ, der den Typ der Daten Satz Variablen definiert, mit dem in der `FileOpen` -Klausel der-Anweisung angegebenen Wert übereinstimmt `Len` .  
  
2. Wenn die Variable in einer `FilePut` `FilePutObject` -oder-Anweisung ist oder eine Zeichenfolge variabler Länge enthält, stellen Sie sicher, dass die Zeichenfolge mit variabler Länge mindestens 2 Zeichen kürzer ist als die in der-Klausel der-Anweisung angegebene Daten Satz Länge `Len` `FileOpen` .  
  
3. Wenn die Variable in einer `FilePut` oder `FilePutObject` ein ist oder ein-Element enthält, `Variant` Stellen Sie sicher, dass die Zeichenfolge mit variabler Länge mindestens 4 Bytes kürzer ist als die in der-Klausel der-Anweisung angegebene Daten Satz Länge `Len` `FileOpen` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
