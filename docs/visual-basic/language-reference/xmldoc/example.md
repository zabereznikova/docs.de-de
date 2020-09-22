---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872974"
---
# <a name="example-visual-basic"></a>\<example> (Visual Basic)

Gibt ein Beispiel für den Member an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Parameter  

 `description`  
 Eine Beschreibung des Codebeispiels.  
  
## <a name="remarks"></a>Hinweise  

 Mit dem `<example>`-Tag kann ein Beispiel für die Verwendung einer Methode oder eines anderen Bibliothekmembers angegeben werden. Dies schließt im Allgemeinen die Verwendung des [\<code>](code.md)-Tags ein.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- `<example>` Tag verwendet, um ein Beispiel für die Verwendung des- `ID` Felds einzufügen.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
