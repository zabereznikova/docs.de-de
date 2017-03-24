---
title: '&lt;Hinweise&gt; (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 89f8d321505b528d07fd04780cec06fb65b0e05e
ms.lasthandoff: 03/13/2017

---
# <a name="ltremarksgt-visual-basic"></a>&lt;Hinweise&gt; (Visual Basic)
Gibt einen Hinweisabschnitt für den Member.  
  
## <a name="syntax"></a>Syntax  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Elements.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<remarks>` Tag Hinzufügen von Informationen zu einem Typ, der mit angegebenen mittels [ \<Zusammenfassung >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Diese Informationen werden im Objektkatalog angezeigt. Informationen über den Objektkatalog finden Sie unter [Anzeigen der Struktur des Codes](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode.  
  
 [!code-vb[VbVbcnXmlDocComments&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
