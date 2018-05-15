---
title: '&lt;Liste&gt; (Visual Basic)'
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
ms.openlocfilehash: f03924217393e1e909b086b282f1c62ddb471522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltlistgt-visual-basic"></a><span data-ttu-id="7dc7f-102">&lt;Liste&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc7f-102">&lt;list&gt; (Visual Basic)</span></span>
<span data-ttu-id="7dc7f-103">Definiert eine Liste oder Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dc7f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="7dc7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7dc7f-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="7dc7f-106">Der Typ der Liste.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-106">The type of the list.</span></span> <span data-ttu-id="7dc7f-107">Muss eine "Bullet" für eine Liste mit Aufzählungszeichen, "Number" für eine nummerierte Liste oder "Table" für eine zweispaltige Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="7dc7f-108">Nur verwendet, wenn `type` ist "table".</span><span class="sxs-lookup"><span data-stu-id="7dc7f-108">Only used when `type` is "table."</span></span> <span data-ttu-id="7dc7f-109">Ein Ausdruck zum definieren, die in der Beschreibungstag definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="7dc7f-110">Wenn `type` ist "Bullet" oder "number" `description` ist ein Element in der Liste beim `type` ist "table" `description` ist die Definition der `term`.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dc7f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dc7f-111">Remarks</span></span>  
 <span data-ttu-id="7dc7f-112">Die `<listheader>` -Block definiert die Überschrift einer Tabelle oder die Definition.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="7dc7f-113">Wenn Sie eine Tabelle zu definieren, Sie müssen nur ein Eintrag für angegeben `term` in der Überschrift.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="7dc7f-114">Jedes Element in der Liste wird angegeben, mit einer `<item>` Block.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="7dc7f-115">Wenn Sie eine Definitionsliste zu erstellen, müssen Sie beide angeben `term` und `description`.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="7dc7f-116">Allerdings für eine Tabelle, eine Liste mit Aufzählungszeichen oder eine nummerierte Liste, Sie müssen nur ein Eintrag für angegeben `description`.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="7dc7f-117">Eine Liste oder Tabelle können beliebig viele `<item>` blockiert nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="7dc7f-118">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dc7f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dc7f-119">Example</span></span>  
 <span data-ttu-id="7dc7f-120">Dieses Beispiel verwendet die `<list>` -Tag, um eine Liste mit Aufzählungszeichen im Abschnitt "Hinweise" definieren.</span><span class="sxs-lookup"><span data-stu-id="7dc7f-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7dc7f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dc7f-121">See Also</span></span>  
 [<span data-ttu-id="7dc7f-122">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="7dc7f-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
