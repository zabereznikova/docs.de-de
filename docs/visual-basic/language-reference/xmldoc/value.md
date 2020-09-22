---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875170"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)

Gibt die Beschreibung einer Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parameter  

 `property-description`  
 Eine Beschreibung der Eigenschaft  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie das- `<value>` Tag, um eine Eigenschaft zu beschreiben. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung ein [\<summary>](summary.md) Tag für die neue Eigenschaft hinzugefügt wird. Sie sollten dann manuell ein `<value>`-Tag für die Beschreibung des Werts hinzufügen, den die Eigenschaft darstellt.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- `<value>` Tag verwendet, um den Wert der-Eigenschaft zu beschreiben `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
