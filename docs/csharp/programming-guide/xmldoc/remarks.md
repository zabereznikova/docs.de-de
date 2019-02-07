---
title: <remarks> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b290315cd9c36281c110bbf0c6246468a1a899b2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259162"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="938ea-102">\<remarks> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="938ea-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="938ea-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="938ea-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="938ea-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="938ea-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="938ea-105">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="938ea-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="938ea-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="938ea-106">Remarks</span></span>  
 <span data-ttu-id="938ea-107">Das Tag \<remarks> wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) angegebenen Informationen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="938ea-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="938ea-108">Diese Informationen werden im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="938ea-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="938ea-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="938ea-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="938ea-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="938ea-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="938ea-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="938ea-111">See also</span></span>

- [<span data-ttu-id="938ea-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="938ea-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="938ea-113">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="938ea-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
