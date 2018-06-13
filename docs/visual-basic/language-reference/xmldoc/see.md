---
title: '&lt;finden Sie unter&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e790f8abd216e198ff5077beab6f857e39981d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602079"
---
# <a name="ltseegt-visual-basic"></a>&lt;finden Sie unter&gt; (Visual Basic)
Gibt einen Link zu einem anderen Member an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist und übergibt `member` an den Elementnamen in der XML-Ausgabe. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<see>` -Tag, um einen Link im Text angegeben. Verwendung [ \<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) um Text anzugeben, die im Abschnitt "Siehe auch" angezeigt werden sollen.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<see>` -Tag in die `UpdateRecord` "Hinweise" im Abschnitt zum Verweisen auf die `DoesRecordExist` Methode.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
