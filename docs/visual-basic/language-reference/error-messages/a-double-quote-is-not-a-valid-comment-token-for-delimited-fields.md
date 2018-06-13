---
title: Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: 5838ef168523e8ba31fe5db93781bc409690e7ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584138"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.
Als Trennzeichen für den `TextFieldParser`wurde ein Anführungszeichen angegeben, aber `EscapeQuotes` ist auf `True`festgelegt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Legen Sie `EscapeQuotes` auf `False`fest.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>  
 [Gewusst wie: Lesen aus Textdateien mit Kommatrennung](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
