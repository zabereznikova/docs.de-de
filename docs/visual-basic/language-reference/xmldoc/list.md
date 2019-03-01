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
ms.openlocfilehash: 8964b34d94daf18e078e515b65588f5273c76199
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970185"
---
# <a name="list-visual-basic"></a><span data-ttu-id="ded63-102">\<list> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ded63-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="ded63-103">Definiert eine Liste oder Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ded63-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ded63-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ded63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ded63-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="ded63-106">Der Typ der Liste.</span><span class="sxs-lookup"><span data-stu-id="ded63-106">The type of the list.</span></span> <span data-ttu-id="ded63-107">Muss eine "Bullet" für eine Liste mit Aufzählungszeichen, "Number" für eine nummerierte Liste oder "Table" für eine Tabelle mit zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="ded63-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="ded63-108">Nur verwendet, wenn `type` ist "table".</span><span class="sxs-lookup"><span data-stu-id="ded63-108">Only used when `type` is "table."</span></span> <span data-ttu-id="ded63-109">Ein zu definierender Begriff, die in der Beschreibungstag definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ded63-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="ded63-110">Wenn `type` ist "Bullet" oder "number", `description` ist ein Element in der Liste bei `type` ist "table" `description` ist die Definition der `term`.</span><span class="sxs-lookup"><span data-stu-id="ded63-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ded63-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ded63-111">Remarks</span></span>  
 <span data-ttu-id="ded63-112">Die `<listheader>` -Block definiert die Überschrift einer Tabelle oder einer Definition.</span><span class="sxs-lookup"><span data-stu-id="ded63-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="ded63-113">Wenn Sie eine Tabelle zu definieren, Sie müssen nur ein Eintrag für angegeben `term` in der Überschrift.</span><span class="sxs-lookup"><span data-stu-id="ded63-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="ded63-114">Jedes Element in der Liste wird angegeben, mit einem `<item>` Block.</span><span class="sxs-lookup"><span data-stu-id="ded63-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="ded63-115">Beim Erstellen einer Definitionsliste müssen Sie angeben, beide `term` und `description`.</span><span class="sxs-lookup"><span data-stu-id="ded63-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="ded63-116">Allerdings für eine Tabelle, Liste mit Aufzählungszeichen oder nummerierte Liste, Sie müssen nur ein Eintrag für angegeben `description`.</span><span class="sxs-lookup"><span data-stu-id="ded63-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="ded63-117">Eine Liste oder Tabelle lassen sich so viele `<item>` blockiert nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ded63-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="ded63-118">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ded63-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ded63-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ded63-119">Example</span></span>  
 <span data-ttu-id="ded63-120">Dieses Beispiel verwendet die `<list>` Tag, um eine Liste mit Aufzählungszeichen im Abschnitt "Hinweise" definieren.</span><span class="sxs-lookup"><span data-stu-id="ded63-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ded63-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ded63-121">See also</span></span>
- [<span data-ttu-id="ded63-122">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="ded63-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
