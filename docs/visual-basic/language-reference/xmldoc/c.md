---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400162"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)
Gibt an, dass Text in einer Beschreibung Code ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---|---|  
|`text`|Der Text, der als Code angegeben werden soll.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `<c>` Tag bietet Ihnen die Möglichkeit, anzugeben, dass Text in einer Beschreibung als Code gekennzeichnet werden soll. Verwenden [\<code>](code.md) Sie, um mehrere Zeilen als Code anzugeben.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<c>` Tag im Zusammenfassungs Abschnitt verwendet, um anzugeben, dass der `Counter` Code ist.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)
