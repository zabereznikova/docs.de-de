---
title: '&lt;paramref&gt; (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- paramref
- <paramref>
dev_langs:
- CSharp
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 452701c4f70bf6cbc619064d62de552fa54bba65
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="352d0-102">&lt;paramref&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="352d0-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="352d0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="352d0-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="352d0-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="352d0-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="352d0-105">Der Name des Parameters, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="352d0-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="352d0-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="352d0-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="352d0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="352d0-107">Remarks</span></span>  
 <span data-ttu-id="352d0-108">Das Tag \<paramref> bietet Ihnen eine Möglichkeit anzugeben, dass sich ein Wort in den Codekommentaren, z.B. in einem \<summary>- oder \<remarks>-Block, auf einen Parameter bezieht.</span><span class="sxs-lookup"><span data-stu-id="352d0-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="352d0-109">Die XML-Datei kann so verarbeitet werden, dass dieses Wort anders formatiert wird, z.B. fett oder kursiv.</span><span class="sxs-lookup"><span data-stu-id="352d0-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="352d0-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="352d0-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="352d0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="352d0-111">Example</span></span>  
 <span data-ttu-id="352d0-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="352d0-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352d0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="352d0-113">See Also</span></span>  
 <span data-ttu-id="352d0-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="352d0-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="352d0-115">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="352d0-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

