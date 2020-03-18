---
title: <inheritdoc> - C#-Programmierhandbuch
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156947"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="ebf41-102">\<inheritdoc> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ebf41-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ebf41-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebf41-103">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="ebf41-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="ebf41-104">InheritDoc</span></span>

<span data-ttu-id="ebf41-105">XML-Kommentare werden aus Basisklassen, Schnittstellen und ähnlichen Methoden geerbt.</span><span class="sxs-lookup"><span data-stu-id="ebf41-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="ebf41-106">So wird das unerwünschte Kopieren und Einfügen doppelter XML-Kommentare vermieden, und XML-Kommentare werden automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="ebf41-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ebf41-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebf41-107">Remarks</span></span>  
<span data-ttu-id="ebf41-108">Fügen Sie Basisklassen oder Schnittstellen Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die implementierenden Klassen kopieren.</span><span class="sxs-lookup"><span data-stu-id="ebf41-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="ebf41-109">Fügen Sie synchronen Methoden Ihre XML-Kommentare hinzu, und lassen Sie die Kommentare von InheritDoc in die asynchronen Versionen derselben Methoden kopieren.</span><span class="sxs-lookup"><span data-stu-id="ebf41-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="ebf41-110">Wenn Sie die Kommentare aus einem bestimmten Member kopieren möchten, können Sie das `cref`-Attribut zur Angabe des Members verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebf41-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="ebf41-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ebf41-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="ebf41-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebf41-112">See also</span></span>

- [<span data-ttu-id="ebf41-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ebf41-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ebf41-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="ebf41-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
