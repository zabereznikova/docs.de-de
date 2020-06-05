---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400142"
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
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie das- `<code>` Tag, um mehrere Zeilen als Code anzugeben. Verwenden [\<c>](c.md) Sie, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- \<code> Tag verwendet, um Beispielcode für die Verwendung des- `ID` Felds einzufügen.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
