---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524675"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="015e6-102">\<remarks > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="015e6-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="015e6-103">Gibt einen Abschnitt mit Hinweisen für den Member an.</span><span class="sxs-lookup"><span data-stu-id="015e6-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="015e6-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="015e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="015e6-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="015e6-106">Eine Beschreibung des Members</span><span class="sxs-lookup"><span data-stu-id="015e6-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="015e6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="015e6-107">Remarks</span></span>  
 <span data-ttu-id="015e6-108">Verwenden Sie das `<remarks>`-Tag, um Informationen zu einem Typ hinzuzufügen, und ergänzen Sie die mit [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)angegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="015e6-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="015e6-109">Diese Informationen werden in der Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="015e6-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="015e6-110">Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="015e6-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="015e6-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="015e6-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="015e6-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="015e6-112">Example</span></span>  
 <span data-ttu-id="015e6-113">In diesem Beispiel wird das `<remarks>`-Tag verwendet, um zu erläutern, was die `UpdateRecord` Methode bewirkt.</span><span class="sxs-lookup"><span data-stu-id="015e6-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="015e6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="015e6-114">See also</span></span>

- [<span data-ttu-id="015e6-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="015e6-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
