---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524675"
---
# <a name="remarks-visual-basic"></a>\<remarks > (Visual Basic)
Gibt einen Abschnitt mit Hinweisen für den Member an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<remarks>`-Tag, um Informationen zu einem Typ hinzuzufügen, und ergänzen Sie die mit [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)angegebenen Informationen.  
  
 Diese Informationen werden in der Objektkatalog angezeigt. Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<remarks>`-Tag verwendet, um zu erläutern, was die `UpdateRecord` Methode bewirkt.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
