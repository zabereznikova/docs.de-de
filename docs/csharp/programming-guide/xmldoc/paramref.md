---
title: '&lt;paramref&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 0e837a3acdd6316446327453af4508f501a9437b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518350"
---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="b17e5-102">&lt;paramref&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b17e5-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b17e5-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="b17e5-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b17e5-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="b17e5-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b17e5-105">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b17e5-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="b17e5-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="b17e5-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b17e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b17e5-107">Remarks</span></span>  
 <span data-ttu-id="b17e5-108">Das Tag \<paramref> bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z.B. in einem \<summary>- oder \<remarks>-Block, auf einen Parameter bezieht.</span><span class="sxs-lookup"><span data-stu-id="b17e5-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="b17e5-109">Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.</span><span class="sxs-lookup"><span data-stu-id="b17e5-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="b17e5-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b17e5-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b17e5-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b17e5-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b17e5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b17e5-112">See Also</span></span>

- [<span data-ttu-id="b17e5-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b17e5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b17e5-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="b17e5-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
