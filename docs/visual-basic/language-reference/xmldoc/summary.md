---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 3bc4393d2fa14f804c6383780e238b1ac2610a94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352200"
---
# <a name="summary-visual-basic"></a>\<Zusammenfassungs > (Visual Basic)
Gibt die Zusammenfassung des Members an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Übersicht des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<summary>`-Tag, um einen Typ oder einen Typmember zu beschreiben. Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.  
  
 Der Text für das `<summary>`-Tag ist die einzige Quelle für Informationen über den Typ in IntelliSense und wird auch in der Objektkatalog angezeigt. Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet das `<summary>`-Tag, um die `ResetCounter`-Methode und die `Counter`-Eigenschaft zu beschreiben.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
