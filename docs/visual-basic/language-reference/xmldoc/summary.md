---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 471d3ddb5cf5a234cb77de6d1d93309faf754359
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865843"
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
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie das- `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.  
  
 Der Text für das- `<summary>` Tag ist die einzige Quelle von Informationen über den Typ in IntelliSense und wird auch in der Objektkatalog angezeigt. Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel werden die-Methode und die-Eigenschaft mithilfe des- `<summary>` Tags beschrieben `ResetCounter` `Counter` .  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
