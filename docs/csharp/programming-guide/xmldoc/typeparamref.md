---
title: '&lt;typeparamref&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: bbe9bed5a32e463424b98f4066e95374401931e2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243919"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a>&lt;typeparamref&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name des Typparameters. Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Typparametern in generischen Typen und Methoden, finden Sie unter [Generika](../../../csharp/programming-guide/generics/index.md).  
  
 Verwenden Sie dieses Tag, um Consumern der Dokumentationsdatei zu ermöglichen, das Wort auf unterschiedliche Weise zu formatieren, z.B. in Kursivschrift.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
