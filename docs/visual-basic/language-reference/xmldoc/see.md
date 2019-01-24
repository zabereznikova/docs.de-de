---
title: '&lt;see&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: afc67d744a04f404a275077ecac42556c963d472
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721968"
---
# <a name="ltseegt-visual-basic"></a>&lt;see&gt; (Visual Basic)
Gibt einen Link zu einem anderen Member an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<see>` Tag, um einen Link im Text angegeben. Verwendung [ \<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) um Text anzugeben, die möglicherweise in einem Abschnitt "Siehe auch" angezeigt werden sollen.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<see>` -Tag in die `UpdateRecord` Hinweise im Abschnitt zum Verweisen auf die `DoesRecordExist` Methode.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
