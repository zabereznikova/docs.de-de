---
title: '&lt;Zusammenfassung&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 899a3343d9758aab79f5aaa77ede26e92f8c07ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551007"
---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="eea66-102">&lt;Zusammenfassung&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eea66-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="eea66-103">Gibt an, die Zusammenfassung des Elements.</span><span class="sxs-lookup"><span data-stu-id="eea66-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eea66-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eea66-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eea66-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="eea66-106">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="eea66-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eea66-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eea66-107">Remarks</span></span>  
 <span data-ttu-id="eea66-108">Verwenden der `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="eea66-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="eea66-109">Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eea66-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="eea66-110">Der Text für die `<summary>` -Tag ist die einzige Quelle für Informationen zu den Typ in IntelliSense und wird auch im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eea66-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="eea66-111">Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="eea66-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="eea66-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="eea66-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eea66-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eea66-113">Example</span></span>  
 <span data-ttu-id="eea66-114">Dieses Beispiel verwendet die `<summary>` Tag zum Beschreiben der `ResetCounter` Methode und `Counter` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eea66-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eea66-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eea66-115">See also</span></span>
- [<span data-ttu-id="eea66-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="eea66-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
