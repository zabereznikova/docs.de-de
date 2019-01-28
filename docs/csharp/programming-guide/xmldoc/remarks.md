---
title: '&lt;remarks&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: faeb1b07d4778f56ae854d5ece93588cbe5848f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536047"
---
# <a name="ltremarksgt-c-programming-guide"></a>&lt;remarks&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parameter  
 `Description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Das Tag \<remarks> wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) angegebenen Informationen ergänzt. Diese Informationen werden im Fenster des Objektkatalogs angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
