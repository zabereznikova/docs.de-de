---
title: Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: b49a3223c6638adff757d7d82aee549cb1fee473
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646928"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.
Als Trennzeichen für den `TextFieldParser`wurde ein Anführungszeichen angegeben, aber `EscapeQuotes` ist auf `True`festgelegt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Legen Sie `EscapeQuotes` auf `False` fest.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Vorgehensweise: Lesen aus durch Trennzeichen getrennten Textdateien](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
