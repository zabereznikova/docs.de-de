---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873035"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)

Gibt an, dass der Text mehrere Codezeilen ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parameter  

 `content`  
 Der Text, der als Code markiert werden soll.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie das- `<code>` Tag, um mehrere Zeilen als Code anzugeben. Verwenden [\<c>](c.md) Sie, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- \<code> Tag verwendet, um Beispielcode für die Verwendung des- `ID` Felds einzufügen.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [XML-Kommentartags](index.md)
