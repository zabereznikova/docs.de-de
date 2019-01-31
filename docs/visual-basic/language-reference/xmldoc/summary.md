---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 3f40177b717452f316672c29c6455faf33e01b4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282710"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="13be8-102">\<summary > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13be8-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="13be8-103">Gibt an, die Zusammenfassung des Elements.</span><span class="sxs-lookup"><span data-stu-id="13be8-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13be8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13be8-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13be8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13be8-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="13be8-106">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="13be8-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13be8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13be8-107">Remarks</span></span>  
 <span data-ttu-id="13be8-108">Verwenden der `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="13be8-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="13be8-109">Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="13be8-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="13be8-110">Der Text für die `<summary>` -Tag ist die einzige Quelle für Informationen zu den Typ in IntelliSense und wird auch im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="13be8-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="13be8-111">Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="13be8-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="13be8-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="13be8-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13be8-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13be8-113">Example</span></span>  
 <span data-ttu-id="13be8-114">Dieses Beispiel verwendet die `<summary>` Tag zum Beschreiben der `ResetCounter` Methode und `Counter` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="13be8-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="13be8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13be8-115">See also</span></span>
- [<span data-ttu-id="13be8-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="13be8-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
