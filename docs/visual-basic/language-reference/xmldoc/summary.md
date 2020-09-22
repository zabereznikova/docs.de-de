---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 471d3ddb5cf5a234cb77de6d1d93309faf754359
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865843"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="28285-101">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28285-101">\<summary> (Visual Basic)</span></span>

<span data-ttu-id="28285-102">Gibt die Zusammenfassung des Members an.</span><span class="sxs-lookup"><span data-stu-id="28285-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28285-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="28285-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="28285-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="28285-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="28285-105">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="28285-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28285-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28285-106">Remarks</span></span>  

 <span data-ttu-id="28285-107">Verwenden Sie das- `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="28285-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="28285-108">Verwenden Sie [\<remarks>](remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="28285-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="28285-109">Der Text für das- `<summary>` Tag ist die einzige Quelle von Informationen über den Typ in IntelliSense und wird auch in der Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28285-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="28285-110">Weitere Informationen zum Objektkatalog finden Sie unter [Anzeigen der Code Struktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="28285-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="28285-111">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="28285-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28285-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28285-112">Example</span></span>  

 <span data-ttu-id="28285-113">In diesem Beispiel werden die-Methode und die-Eigenschaft mithilfe des- `<summary>` Tags beschrieben `ResetCounter` `Counter` .</span><span class="sxs-lookup"><span data-stu-id="28285-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="28285-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28285-114">See also</span></span>

- [<span data-ttu-id="28285-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="28285-115">XML Comment Tags</span></span>](index.md)
