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
ms.openlocfilehash: b2e91b868c35773033418c796b7c43b08e87a28b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480376"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="c730d-102">\<remarks> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c730d-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c730d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c730d-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c730d-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="c730d-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="c730d-105">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="c730d-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c730d-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c730d-106">Remarks</span></span>  
 <span data-ttu-id="c730d-107">Das Tag \<remarks> wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) angegebenen Informationen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="c730d-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="c730d-108">Diese Informationen werden im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c730d-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="c730d-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c730d-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c730d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c730d-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c730d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c730d-111">See also</span></span>

- [<span data-ttu-id="c730d-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c730d-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c730d-113">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="c730d-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
