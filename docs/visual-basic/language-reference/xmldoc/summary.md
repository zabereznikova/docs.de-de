---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: e629a738a706b09dec97dd6593ef493470ec9472
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473876"
---
# <a name="summary-visual-basic"></a>\<summary > (Visual Basic)
Gibt an, die Zusammenfassung des Elements.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Übersicht des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.  
  
 Der Text für die `<summary>` -Tag ist die einzige Quelle für Informationen zu den Typ in IntelliSense und wird auch im Objektkatalog angezeigt. Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<summary>` Tag zum Beschreiben der `ResetCounter` Methode und `Counter` Eigenschaft.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
