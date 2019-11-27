---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352250"
---
# <a name="remarks-visual-basic"></a>\<Hinweise > (Visual Basic)
Gibt einen Abschnitt mit Hinweisen für den Member an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<remarks>`-Tag, um Informationen zu einem Typ hinzuzufügen, und ergänzen Sie die mit [\<Zusammenfassungs >](../../../visual-basic/language-reference/xmldoc/summary.md)angegebenen Informationen.  
  
 Diese Informationen werden in der Objektkatalog angezeigt. Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<remarks>`-Tag verwendet, um zu erläutern, was die `UpdateRecord` Methode bewirkt.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
