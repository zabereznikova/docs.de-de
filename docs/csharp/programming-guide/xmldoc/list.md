---
title: '&lt;list&gt; (C# -Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
dev_langs:
- CSharp
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
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
ms.openlocfilehash: b9d3dfa60530734a142295c8a8f2c32c4ecd9a47
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="b1fdb-102">&lt;list&gt; (C# -Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b1fdb-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b1fdb-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1fdb-103">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b1fdb-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1fdb-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="b1fdb-105">Ein zu definierender Begriff, der in `description` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="b1fdb-106">Entweder ein Element einer Aufzählung oder nummerierten Liste oder die Definition eines `term`.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1fdb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1fdb-107">Remarks</span></span>  
 <span data-ttu-id="b1fdb-108">Der \<listheader>-Block wird verwendet, um die Überschriftenzeile einer Tabelle oder einer Definitionsliste zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="b1fdb-109">Bei der Definition einer Tabelle müssen Sie nur einen Eintrag für „term“ in der Überschrift angeben.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="b1fdb-110">Jedes Element der Liste wird mit einem \<item>-Block angegeben.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="b1fdb-111">Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="b1fdb-112">Für eine Tabelle, eine Auflistung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="b1fdb-113">Eine Liste oder Tabelle kann so viele \<item>-Blöcke besitzen wie nötig.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="b1fdb-114">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b1fdb-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1fdb-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1fdb-115">Example</span></span>  
 <span data-ttu-id="b1fdb-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1fdb-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fdb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1fdb-117">See Also</span></span>  
 <span data-ttu-id="b1fdb-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1fdb-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b1fdb-119">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="b1fdb-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

