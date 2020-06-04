---
title: Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 0e81652a0f9e97ce40851170ed050bd1f047ba5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412935"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein. Ein Feld mit einer Breite unter oder gleich 0 (null) im letzten Element bedeutet, dass die Länge des letzten Felds variabel ist.  
  
 Der Vorgang ist fehlgeschlagen, da die Feldbreite eines anderen Elements, das nicht das letzte Element ist, auf 0 (null) oder kleiner festgelegt ist. Eine Feldbreite, die kleiner oder gleich 0 (null) ist, kann als letztes Element verwendet werden, um anzugeben, dass dass die Länge des letzten Felds variabel ist. Sie kann jedoch nicht als ein anderes Element verwendet werden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Legen Sie die Feldbreite auf die richtige Länge fest.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Vorgehensweise: Lesen aus Textdateien mit fester Breite](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
