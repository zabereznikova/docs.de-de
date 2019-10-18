---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524628"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="d3b52-102">\<summary > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3b52-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="d3b52-103">Gibt die Zusammenfassung des Members an.</span><span class="sxs-lookup"><span data-stu-id="d3b52-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3b52-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3b52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3b52-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d3b52-106">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="d3b52-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3b52-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3b52-107">Remarks</span></span>  
 <span data-ttu-id="d3b52-108">Verwenden Sie das `<summary>`-Tag, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d3b52-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="d3b52-109">Verwenden Sie [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3b52-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="d3b52-110">Der Text für das `<summary>`-Tag ist die einzige Quelle für Informationen über den Typ in IntelliSense und wird auch in der Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b52-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="d3b52-111">Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="d3b52-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="d3b52-112">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3b52-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b52-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3b52-113">Example</span></span>  
 <span data-ttu-id="d3b52-114">Dieses Beispiel verwendet das `<summary>`-Tag, um die `ResetCounter`-Methode und die `Counter`-Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d3b52-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d3b52-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3b52-115">See also</span></span>

- [<span data-ttu-id="d3b52-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d3b52-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
