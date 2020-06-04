---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411472"
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
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie das- `<value>` Tag, um eine Eigenschaft zu beschreiben. Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung ein [\<summary>](summary.md) Tag für die neue Eigenschaft hinzugefügt wird. Sie sollten dann manuell ein- `<value>` Tag hinzufügen, um den Wert zu beschreiben, den die-Eigenschaft darstellt.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<value>` Tag verwendet, um den Wert der-Eigenschaft zu beschreiben `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
