---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524618"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="d25d7-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d25d7-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="d25d7-103">Definiert einen Typparameter Namen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="d25d7-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d25d7-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d25d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d25d7-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d25d7-106">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="d25d7-106">The name of the type parameter.</span></span> <span data-ttu-id="d25d7-107">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="d25d7-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d25d7-108">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="d25d7-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d25d7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d25d7-109">Remarks</span></span>  
 <span data-ttu-id="d25d7-110">Verwenden Sie das `<typeparam>`-Tag im Kommentar für einen generischen Typ oder eine generische Element Deklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d25d7-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="d25d7-111">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d25d7-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d25d7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d25d7-112">Example</span></span>  
 <span data-ttu-id="d25d7-113">In diesem Beispiel wird das `<typeparam>`-Tag verwendet, um den `id`-Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d25d7-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="d25d7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d25d7-114">See also</span></span>

- [<span data-ttu-id="d25d7-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d25d7-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
