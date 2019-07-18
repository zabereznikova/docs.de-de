---
title: TextFieldParser unterstützt keine Kommentartoken, die Leerzeichen enthalten.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: af0f09bb7a8afc3b6e63cfab1a7176ba26cf20a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660899"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser unterstützt keine Kommentartoken, die Leerzeichen enthalten.
Es wurde ein Kommentartoken bereitgestellt, das Leerzeichen enthält. Der `TextFieldParser` unterstützt keine Kommentartoken, die Leerzeichen enthalten, es sei denn, die Leerzeichen befinden sich am Anfang des Tokens. Leerzeichen, die sich am Anfang eines Tokens befinden, werden ignoriert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Geben Sie ein ordnungsgemäßes Kommentartoken an.  
  
## <a name="see-also"></a>Siehe auch

- [TextFieldParser.CommentTokens Property](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser-Objekt](../../visual-basic/language-reference/objects/textfieldparser-object.md)
