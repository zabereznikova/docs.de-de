---
title: '&lt;list&gt; (C# -Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 768490424403f1235873a681ffba3367e3f128b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="b35fd-102">&lt;list&gt; (C# -Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b35fd-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b35fd-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="b35fd-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b35fd-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="b35fd-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="b35fd-105">Ein zu definierender Begriff, der in `description` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b35fd-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="b35fd-106">Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.</span><span class="sxs-lookup"><span data-stu-id="b35fd-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b35fd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b35fd-107">Remarks</span></span>  
 <span data-ttu-id="b35fd-108">Der \<listheader>-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b35fd-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="b35fd-109">Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.</span><span class="sxs-lookup"><span data-stu-id="b35fd-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="b35fd-110">Jedes Element der Liste wird mit einem \<item>-Block angegeben.</span><span class="sxs-lookup"><span data-stu-id="b35fd-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="b35fd-111">Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.</span><span class="sxs-lookup"><span data-stu-id="b35fd-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="b35fd-112">Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b35fd-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="b35fd-113">Eine Liste oder Tabelle kann so viele \<item>-Blöcke besitzen wie nötig.</span><span class="sxs-lookup"><span data-stu-id="b35fd-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="b35fd-114">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b35fd-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b35fd-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b35fd-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b35fd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b35fd-116">See Also</span></span>  
 [<span data-ttu-id="b35fd-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b35fd-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b35fd-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="b35fd-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
