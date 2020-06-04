---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411472"
---
# <a name="value-visual-basic"></a><span data-ttu-id="c629d-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c629d-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="c629d-102">Gibt die Beschreibung einer Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c629d-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c629d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c629d-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c629d-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="c629d-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="c629d-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c629d-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c629d-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c629d-106">Remarks</span></span>  
 <span data-ttu-id="c629d-107">Verwenden Sie das- `<value>` Tag, um eine Eigenschaft zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c629d-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="c629d-108">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Visual Studio-Entwicklungsumgebung ein [\<summary>](summary.md) Tag für die neue Eigenschaft hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c629d-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="c629d-109">Sie sollten dann manuell ein- `<value>` Tag hinzufügen, um den Wert zu beschreiben, den die-Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="c629d-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="c629d-110">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c629d-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c629d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c629d-111">Example</span></span>  
 <span data-ttu-id="c629d-112">In diesem Beispiel wird das- `<value>` Tag verwendet, um den Wert der-Eigenschaft zu beschreiben `Counter` .</span><span class="sxs-lookup"><span data-stu-id="c629d-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c629d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c629d-113">See also</span></span>

- [<span data-ttu-id="c629d-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c629d-114">XML Comment Tags</span></span>](index.md)
