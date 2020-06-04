---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411498"
---
# <a name="summary-visual-basic"></a>\<summary> (Visual Basic)
Gibt die Zusammenfassung des Members an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Übersicht des Objekts.  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie das- `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](remarks.md) , um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.  
  
 Der Text für das- `<summary>` Tag ist die einzige Quelle von Informationen über den Typ in IntelliSense und wird auch in der Objektkatalog angezeigt. Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die-Methode und die-Eigenschaft mithilfe des- `<summary>` Tags beschrieben `ResetCounter` `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
