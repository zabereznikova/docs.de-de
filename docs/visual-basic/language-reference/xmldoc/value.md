---
title: '&lt;Wert&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a>&lt;Wert&gt; (Visual Basic)
Gibt die Beschreibung einer Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parameter  
 `property-description`  
 Eine Beschreibung der Eigenschaft  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<value>` -Tag, um eine Eigenschaft zu beschreiben. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mit dem Code-Assistenten in der Visual Studio-Entwicklungsumgebung hinzufügen wird ein [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft. Sie sollten dann manuell hinzufügen einer `<value>` -Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
