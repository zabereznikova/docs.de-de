---
title: '&lt;Wert&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 92c8c2ac7b95e97b37c907e3837bc90dac384b33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558942"
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
 Verwenden der `<value>` Tag, um eine Eigenschaft beschreiben. Beachten Sie, dass wenn Sie eine Eigenschaft mit dem Code-Assistenten in der Entwicklungsumgebung von Visual Studio hinzufügen, wird es Hinzufügen einer [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft. Sie sollten dann manuell hinzufügen einer `<value>` Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
