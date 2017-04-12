---
title: '&lt;Zusammenfassung&gt; (Visual Basic) | Microsoft-Dokumentation'
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ad2053e21e58c49205fe869a484cb2dffd2169ee
ms.lasthandoff: 03/13/2017

---
# <a name="ltsummarygt-visual-basic"></a>&lt;Zusammenfassung&gt; (Visual Basic)
Gibt die Zusammenfassung des Elements an.  
  
## <a name="syntax"></a>Syntax  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Zusammenfassung des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben. Verwendung [ \<Hinweise >](../../../visual-basic/language-reference/xmldoc/remarks.md) zusätzliche Informationen zur eine Beschreibung hinzu.  
  
 Der Text für die `<summary>` -Tag ist die einzige Quelle von Informationen über den Typ in IntelliSense und wird auch im Objektkatalog angezeigt. Informationen über den Objektkatalog finden Sie unter [Anzeigen der Struktur des Codes](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<summary>` Tag beschreiben die `ResetCounter` Methode und `Counter` Eigenschaft.  
  
 [!code-vb[VbVbcnXmlDocComments&#1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
