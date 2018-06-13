---
title: Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: e8026cc7c122d37c135db28813353f7e37f200e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598439"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein. Ein Feld mit einer Breite unter oder gleich 0 (null) im letzten Element bedeutet, dass die Länge des letzten Felds variabel ist.  
  
 Der Vorgang ist fehlgeschlagen, da die Feldbreite eines anderen Elements, das nicht das letzte Element ist, auf 0 (null) oder kleiner festgelegt ist. Eine Feldbreite, die kleiner oder gleich 0 (null) ist, kann als letztes Element verwendet werden, um anzugeben, dass dass die Länge des letzten Felds variabel ist. Sie kann jedoch nicht als ein anderes Element verwendet werden.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Legen Sie die Feldbreite auf die richtige Länge fest.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>  
 [Gewusst wie: Lesen aus einer Textdatei mit fester Breite](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)  
 [TextFieldParser-Objekt](../../visual-basic/language-reference/objects/textfieldparser-object.md)
