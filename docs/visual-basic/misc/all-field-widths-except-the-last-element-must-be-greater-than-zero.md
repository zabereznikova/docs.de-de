---
title: "Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein."
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b348494c0a3103641d29998218b546de0d432e2a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
