---
title: '&lt;paramref&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 90c22b81f17adb1fcfdb94f32047e85c0bd8f4e5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243621"
---
# <a name="ltparamrefgt-c-programming-guide"></a>&lt;paramref&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Parameters, auf den verwiesen wird. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
## <a name="remarks"></a>Hinweise  
 Das Tag \<paramref> bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z.B. in einem \<summary>- oder \<remarks>-Block, auf einen Parameter bezieht. Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
