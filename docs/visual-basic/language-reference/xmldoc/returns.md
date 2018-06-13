---
title: '&lt;Gibt&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: effc55bd65ae6c54575b7931529499505a9523cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598364"
---
# <a name="ltreturnsgt-visual-basic"></a>&lt;Gibt&gt; (Visual Basic)
Gibt den Rückgabewert der Eigenschaft oder Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Rückgabewerts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<returns>` Tag im Kommentar für eine Methodendeklaration, um den Rückgabewert beschreiben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<returns>` -Tag erläutert, was die `DoesRecordExist` -Funktion zurückgegeben wird.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
