---
title: TextFieldParser unterstützt keine Kommentar Token, die Leerzeichen enthalten.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078501"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser unterstützt keine Kommentar Token, die Leerzeichen enthalten.

Es wurde ein Kommentartoken bereitgestellt, das Leerzeichen enthält. Der `TextFieldParser` unterstützt keine Kommentartoken, die Leerzeichen enthalten, es sei denn, die Leerzeichen befinden sich am Anfang des Tokens. Leerzeichen, die sich am Anfang eines Tokens befinden, werden ignoriert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Geben Sie ein ordnungsgemäßes Kommentartoken an.  
  
## <a name="see-also"></a>Siehe auch

- [TextFieldParser.CommentTokens-Eigenschaft](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analysieren von Textdateien mit dem TextFieldParser-Objekt](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
