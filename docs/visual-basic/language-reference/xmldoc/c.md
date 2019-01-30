---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 2fa6e66771ac854421d07a5f33e116f12516dad6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260198"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Gibt an, dass Text in einer Beschreibung Code ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---|---|  
|`text`|Der Text, der als Code angegeben werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<c>` -Tag ermöglicht es eine Möglichkeit, um anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll. Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) verwendet.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<c>` -Tag im Abschnitt "Zusammenfassung" gibt an, dass `Counter` Code.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
