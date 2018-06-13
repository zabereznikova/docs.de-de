---
title: '&lt;"Hinweise"&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 6e4e280760b9238fdc403ac5fe586743334e4c69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598186"
---
# <a name="ltremarksgt-visual-basic"></a>&lt;"Hinweise"&gt; (Visual Basic)
Gibt einen Abschnitt "Hinweise" für das Element an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<remarks>` -Tag, um Informationen über einen Typ, ergänzen die Informationen, die mit angegebenen hinzufügen [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Diese Informationen werden im Objektkatalog angezeigt. Informationen über den Objektkatalog finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode hat.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
