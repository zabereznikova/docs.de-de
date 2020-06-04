---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: edbc374332bdcd67b385ac3d061045664e942460
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84399994"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="70690-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70690-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="70690-102">Gibt den Rückgabewert der Eigenschaft oder Funktion an.</span><span class="sxs-lookup"><span data-stu-id="70690-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70690-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="70690-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="70690-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="70690-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="70690-105">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="70690-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70690-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70690-106">Remarks</span></span>  
 <span data-ttu-id="70690-107">Verwenden Sie das- `<returns>` Tag im Kommentar für eine Methoden Deklaration, um den Rückgabewert zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="70690-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="70690-108">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="70690-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70690-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70690-109">Example</span></span>  
 <span data-ttu-id="70690-110">In diesem Beispiel wird das- `<returns>` Tag verwendet, um die Rückgabe der Funktion zu erläutern `DoesRecordExist` .</span><span class="sxs-lookup"><span data-stu-id="70690-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="70690-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70690-111">See also</span></span>

- [<span data-ttu-id="70690-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="70690-112">XML Comment Tags</span></span>](index.md)
