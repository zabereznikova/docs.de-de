---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524037"
---
# <a name="code-visual-basic"></a>\<code > (Visual Basic)
Gibt an, dass der Text mehrere Codezeilen ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parameter  
 `content`  
 Der Text, der als Code markiert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<code>`-Tag, um mehrere Zeilen als Code anzugeben. Mit [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) wird angegeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  
  
 Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das \<code >-Tags verwendet, um Beispielcode für die Verwendung des `ID`-Felds einzuschließen.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
