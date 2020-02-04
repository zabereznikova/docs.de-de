---
title: <inheritdoc> – C#-Programmierhandbuch
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794834"
---
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a>InheritDoc

XML-Kommentare werden aus Basisklassen, Schnittstellen und ähnlichen Methoden geerbt. So wird das unerwünschte Kopieren und Einfügen doppelter XML-Kommentare vermieden, und XML-Kommentare werden automatisch synchronisiert. 
  
## <a name="remarks"></a>Hinweise  
Fügen Sie Basisklassen oder Schnittstellen Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die implementierenden Klassen kopieren.

Fügen Sie synchronen Methoden Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die asynchronen Versionen derselben Methoden kopieren.  

Wenn Sie die Kommentare aus einem bestimmten Member kopieren möchten, können Sie das `cref`-Attribut zur Angabe des Members verwenden.
  
## <a name="examples"></a>Beispiele
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
