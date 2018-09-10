---
title: '&lt;c&gt; (C# -Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 2220c42485674eaa4ba4e3b2dfb03865ad8013cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508146"
---
# <a name="ltcgt-c-programming-guide"></a>&lt;c&gt; (C# -Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parameter  
 `text`  
 Der Text, der als Code angegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Mit dem \<c>-Tag kann angegeben werden, dass Text in einer Beschreibung als Code gekennzeichnet werden soll. Zum Angeben mehrerer Zeilen als Code wird [\<code>](../../../csharp/programming-guide/xmldoc/code.md) verwendet.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
