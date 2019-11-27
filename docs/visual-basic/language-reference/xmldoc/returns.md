---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352245"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="8a38e-101">\<gibt > (Visual Basic) zurück.</span><span class="sxs-lookup"><span data-stu-id="8a38e-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="8a38e-102">Gibt den Rückgabewert der Eigenschaft oder Funktion an.</span><span class="sxs-lookup"><span data-stu-id="8a38e-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a38e-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a38e-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a38e-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a38e-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="8a38e-105">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="8a38e-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a38e-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a38e-106">Remarks</span></span>  
 <span data-ttu-id="8a38e-107">Verwenden Sie das `<returns>`-Tag im Kommentar für eine Methoden Deklaration, um den Rückgabewert zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8a38e-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="8a38e-108">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8a38e-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a38e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a38e-109">Example</span></span>  
 <span data-ttu-id="8a38e-110">In diesem Beispiel wird das `<returns>`-Tag verwendet, um die Rückgabe der `DoesRecordExist`-Funktion zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="8a38e-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8a38e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a38e-111">See also</span></span>

- [<span data-ttu-id="8a38e-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="8a38e-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
