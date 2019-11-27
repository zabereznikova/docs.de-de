---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352177"
---
# <a name="value-visual-basic"></a>\<Wert > (Visual Basic)
Gibt die Beschreibung einer Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parameter  
 `property-description`  
 Eine Beschreibung der Eigenschaft  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<value>`-Tag, um eine Eigenschaft zu beschreiben. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung eine [\<Zusammenfassungs >](../../../visual-basic/language-reference/xmldoc/summary.md) -Tags für die neue Eigenschaft hinzugefügt wird. Sie sollten dann manuell ein `<value>`-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<value>`-Tag verwendet, um den Wert zu beschreiben, den die `Counter` Eigenschaft enthält.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
