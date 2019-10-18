---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524750"
---
# <a name="list-visual-basic"></a><span data-ttu-id="ca324-102">\<list > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca324-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="ca324-103">Definiert eine Liste oder Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ca324-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca324-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca324-104">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
## <a name="parameters"></a><span data-ttu-id="ca324-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca324-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="ca324-106">Der Typ der Liste.</span><span class="sxs-lookup"><span data-stu-id="ca324-106">The type of the list.</span></span> <span data-ttu-id="ca324-107">Muss ein "Aufzählungs Zeichen" für eine Aufzählungs Liste, "Zahl" für eine nummerierte Liste oder "Table" für eine Tabelle mit zwei Spalten sein.</span><span class="sxs-lookup"><span data-stu-id="ca324-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="ca324-108">Wird nur verwendet, wenn `type` "Table" ist.</span><span class="sxs-lookup"><span data-stu-id="ca324-108">Only used when `type` is "table."</span></span> <span data-ttu-id="ca324-109">Ein zu definierenden Begriff, der im Beschreibungs-Tag definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca324-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="ca324-110">Wenn `type` "Bullet" oder "Number" ist, ist `description` ein Element in der Liste, wenn `type` "Table" ist. `description` ist die Definition des `term`.</span><span class="sxs-lookup"><span data-stu-id="ca324-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca324-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca324-111">Remarks</span></span>  
 <span data-ttu-id="ca324-112">Der `<listheader>`-Block definiert die Überschrift einer Tabelle oder einer Definitionsliste.</span><span class="sxs-lookup"><span data-stu-id="ca324-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="ca324-113">Wenn Sie eine Tabelle definieren, müssen Sie in der Überschrift nur einen Eintrag für `term` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ca324-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="ca324-114">Jedes Element in der Liste wird mit einem `<item>`-Block angegeben.</span><span class="sxs-lookup"><span data-stu-id="ca324-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="ca324-115">Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.</span><span class="sxs-lookup"><span data-stu-id="ca324-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="ca324-116">Für eine Tabelle, eine aufzählige Liste oder eine nummerierte Liste müssen Sie jedoch nur einen Eintrag für `description` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ca324-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="ca324-117">Eine Liste oder Tabelle kann beliebig viele `<item>` Blöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="ca324-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="ca324-118">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ca324-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca324-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca324-119">Example</span></span>  
 <span data-ttu-id="ca324-120">In diesem Beispiel wird das `<list>`-Tag zum Definieren einer aufzurufenden Liste im Abschnitt "Hinweise" verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca324-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ca324-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca324-121">See also</span></span>

- [<span data-ttu-id="ca324-122">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="ca324-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
