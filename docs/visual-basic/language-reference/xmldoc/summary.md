---
title: '&lt;Zusammenfassung&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a3008d1393c44aa0ec2398a2bd6afa079013e7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsummarygt-visual-basic"></a>&lt;Zusammenfassung&gt; (Visual Basic)
Gibt die Zusammenfassung des Elements an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Übersicht des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<summary>` -Tag, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.  
  
 Der Text für die `<summary>` Tag ist die einzige Quelle der Informationen über den Typ in IntelliSense und wird auch im Objektkatalog angezeigt. Informationen über den Objektkatalog finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<summary>` Tag beschreiben die `ResetCounter` Methode und `Counter` Eigenschaft.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
