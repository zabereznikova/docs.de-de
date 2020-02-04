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
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="0a1fc-102">\<inheritdoc> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0a1fc-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a1fc-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a1fc-103">Syntax</span></span>  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a><span data-ttu-id="0a1fc-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="0a1fc-104">InheritDoc</span></span>

<span data-ttu-id="0a1fc-105">XML-Kommentare werden aus Basisklassen, Schnittstellen und ähnlichen Methoden geerbt.</span><span class="sxs-lookup"><span data-stu-id="0a1fc-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="0a1fc-106">So wird das unerwünschte Kopieren und Einfügen doppelter XML-Kommentare vermieden, und XML-Kommentare werden automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0a1fc-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0a1fc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a1fc-107">Remarks</span></span>  
<span data-ttu-id="0a1fc-108">Fügen Sie Basisklassen oder Schnittstellen Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die implementierenden Klassen kopieren.</span><span class="sxs-lookup"><span data-stu-id="0a1fc-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="0a1fc-109">Fügen Sie synchronen Methoden Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die asynchronen Versionen derselben Methoden kopieren.</span><span class="sxs-lookup"><span data-stu-id="0a1fc-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="0a1fc-110">Wenn Sie die Kommentare aus einem bestimmten Member kopieren möchten, können Sie das `cref`-Attribut zur Angabe des Members verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a1fc-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="0a1fc-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0a1fc-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="0a1fc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a1fc-112">See also</span></span>

- [<span data-ttu-id="0a1fc-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0a1fc-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0a1fc-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="0a1fc-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
