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
ms.openlocfilehash: 822ca8feafe48402f8217c10ef37fcdb1576c27a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587747"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="a1cf2-102">\<remarks> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a1cf2-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a1cf2-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1cf2-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1cf2-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1cf2-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="a1cf2-105">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="a1cf2-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1cf2-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a1cf2-106">Remarks</span></span>  
 <span data-ttu-id="a1cf2-107">Das Tag \<remarks> wird verwendet, um Informationen zu einem Typ hinzuzufügen. Dadurch werden die mit [\<summary>](./summary.md) angegebenen Informationen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="a1cf2-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="a1cf2-108">Diese Informationen werden im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1cf2-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="a1cf2-109">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a1cf2-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1cf2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1cf2-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a1cf2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1cf2-111">See also</span></span>

- [<span data-ttu-id="a1cf2-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a1cf2-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a1cf2-113">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a1cf2-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
