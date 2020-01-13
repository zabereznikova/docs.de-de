---
title: <paramref> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 42c428b74f0df9d4ca37e85d805db8012670521c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696544"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="5f1f0-102">\<paramref> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="5f1f0-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5f1f0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f1f0-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f1f0-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f1f0-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5f1f0-105">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="5f1f0-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="5f1f0-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f1f0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f1f0-107">Remarks</span></span>  
 <span data-ttu-id="5f1f0-108">Das Tag \<paramref> bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z.B. in einem \<summary>- oder \<remarks>-Block, auf einen Parameter bezieht.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="5f1f0-109">Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="5f1f0-110">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5f1f0-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f1f0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f1f0-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="5f1f0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f1f0-112">See also</span></span>

- [<span data-ttu-id="5f1f0-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5f1f0-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5f1f0-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="5f1f0-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
