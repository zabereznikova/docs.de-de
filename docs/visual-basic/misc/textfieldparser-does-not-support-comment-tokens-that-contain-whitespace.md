---
title: TextFieldParser unterstützt keine Kommentartoken, die Leerzeichen enthalten.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: a8931d67cd728cf98bc4d83044c65fad6642b021
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252804"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser unterstützt keine Kommentartoken, die Leerzeichen enthalten.
Es wurde ein Kommentartoken bereitgestellt, das Leerzeichen enthält. Der `TextFieldParser` unterstützt keine Kommentartoken, die Leerzeichen enthalten, es sei denn, die Leerzeichen befinden sich am Anfang des Tokens. Leerzeichen, die sich am Anfang eines Tokens befinden, werden ignoriert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie ein ordnungsgemäßes Kommentartoken an.  
  
## <a name="see-also"></a>Siehe auch

- [TextFieldParser.CommentTokens-Eigenschaft](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)  
- [Analysieren von Textdateien mit dem TextFieldParser-Objekt](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
- [TextFieldParser-Objekt](../../visual-basic/language-reference/objects/textfieldparser-object.md)
