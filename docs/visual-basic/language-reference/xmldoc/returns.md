---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 37b110cc6e12f11196d2a1c5cc6026d87b453626
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866406"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="55e6b-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55e6b-101">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="55e6b-102">Gibt den Rückgabewert der Eigenschaft oder Funktion an.</span><span class="sxs-lookup"><span data-stu-id="55e6b-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e6b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="55e6b-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e6b-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="55e6b-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="55e6b-105">Eine Beschreibung des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="55e6b-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e6b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55e6b-106">Remarks</span></span>  

 <span data-ttu-id="55e6b-107">Verwenden Sie das- `<returns>` Tag im Kommentar für eine Methoden Deklaration, um den Rückgabewert zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="55e6b-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="55e6b-108">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="55e6b-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55e6b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55e6b-109">Example</span></span>  

 <span data-ttu-id="55e6b-110">In diesem Beispiel wird das- `<returns>` Tag verwendet, um die Rückgabe der Funktion zu erläutern `DoesRecordExist` .</span><span class="sxs-lookup"><span data-stu-id="55e6b-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="55e6b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55e6b-111">See also</span></span>

- [<span data-ttu-id="55e6b-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="55e6b-112">XML Comment Tags</span></span>](index.md)
