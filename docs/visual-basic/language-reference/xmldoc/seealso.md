---
title: '&lt;Seealso&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a1acbf2ee8f416e28987cc9d63dd3bf6d8c2dcf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltseealsogt-visual-basic"></a>&lt;Seealso&gt; (Visual Basic)
Gibt einen Link, der im Abschnitt Siehe auch angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist und übergibt `member` an den Elementnamen in der XML-Ausgabe. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<seealso>` -Tag, um den Text anzugeben, die in einem Abschnitt Siehe auch angezeigt werden sollen. Mit [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) kann ein Link im Text angegeben werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<seealso>` -Tag in die `DoesRecordExist` "Hinweise" im Abschnitt zum Verweisen auf die `UpdateRecord` Methode.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
