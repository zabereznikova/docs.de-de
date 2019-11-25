---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352245"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)
Specifies the return value of the property or function.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Rückgabewerts.  
  
## <a name="remarks"></a>Hinweise  
 Use the `<returns>` tag in the comment for a method declaration to describe the return value.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
