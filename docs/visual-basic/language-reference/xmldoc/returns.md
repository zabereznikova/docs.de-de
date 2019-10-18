---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524686"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="f81dc-102">\<returns > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f81dc-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="f81dc-103">Gibt den Rückgabewert der Eigenschaft oder Funktion an.</span><span class="sxs-lookup"><span data-stu-id="f81dc-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f81dc-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f81dc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f81dc-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="f81dc-106">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="f81dc-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f81dc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f81dc-107">Remarks</span></span>  
 <span data-ttu-id="f81dc-108">Verwenden Sie das `<returns>`-Tag im Kommentar für eine Methoden Deklaration, um den Rückgabewert zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f81dc-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="f81dc-109">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f81dc-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f81dc-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f81dc-110">Example</span></span>  
 <span data-ttu-id="f81dc-111">In diesem Beispiel wird das `<returns>`-Tag verwendet, um die Rückgabe der `DoesRecordExist`-Funktion zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="f81dc-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f81dc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f81dc-112">See also</span></span>

- [<span data-ttu-id="f81dc-113">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="f81dc-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
