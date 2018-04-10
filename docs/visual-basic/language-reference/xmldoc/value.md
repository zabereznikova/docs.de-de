---
title: '&lt;Wert&gt; (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="23f21-102">&lt;Wert&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23f21-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="23f21-103">Gibt die Beschreibung einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23f21-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23f21-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23f21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23f21-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="23f21-106">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="23f21-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23f21-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23f21-107">Remarks</span></span>  
 <span data-ttu-id="23f21-108">Verwenden der `<value>` -Tag, um eine Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="23f21-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="23f21-109">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mit dem Code-Assistenten in der Visual Studio-Entwicklungsumgebung hinzufügen wird ein [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) Tag für die neue Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23f21-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="23f21-110">Sie sollten dann manuell hinzufügen einer `<value>` -Tag, um den Wert zu beschreiben, die die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="23f21-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="23f21-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="23f21-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23f21-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23f21-112">Example</span></span>  
 <span data-ttu-id="23f21-113">Dieses Beispiel verwendet die `<value>` Tag beschrieben, welchen Wert die `Counter` Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="23f21-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="23f21-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23f21-114">See Also</span></span>  
 [<span data-ttu-id="23f21-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="23f21-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
