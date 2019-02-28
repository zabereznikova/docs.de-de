---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: a1dea0bcc40de8dea986e93a25617f607383ec21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969218"
---
# <a name="example-visual-basic"></a>\<Beispiel > (Visual Basic)
Gibt ein Beispiel für das Element an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Codebeispiels.  
  
## <a name="remarks"></a>Hinweise  
 Die `<example>` -Tag können Sie ein Beispiel zur Verwendung einer Methode oder anderen Bibliothekmembers angegeben. Dies schließt im Allgemeinen die Verwendung des [\<code](../../../visual-basic/language-reference/xmldoc/code.md)-Tags ein.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<example>` Tag enthalten ein Beispiel für die Verwendung der `ID` Feld.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
