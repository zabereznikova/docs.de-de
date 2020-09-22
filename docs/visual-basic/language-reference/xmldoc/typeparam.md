---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 0a68cf0a495c2809961e8ec99effa459b0647fec
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866391"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="f7e0a-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7e0a-101">\<typeparam> (Visual Basic)</span></span>

<span data-ttu-id="f7e0a-102">Definiert einen Typparameter Namen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e0a-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7e0a-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7e0a-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7e0a-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="f7e0a-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-105">The name of the type parameter.</span></span> <span data-ttu-id="f7e0a-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="f7e0a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f7e0a-107">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7e0a-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7e0a-108">Remarks</span></span>  

 <span data-ttu-id="f7e0a-109">Verwenden Sie das- `<typeparam>` Tag im Kommentar für einen generischen Typ oder eine generische Element Deklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f7e0a-110">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7e0a-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7e0a-111">Example</span></span>  

 <span data-ttu-id="f7e0a-112">In diesem Beispiel wird das- `<typeparam>` Tag zum Beschreiben des- `id` Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7e0a-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f7e0a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7e0a-113">See also</span></span>

- [<span data-ttu-id="f7e0a-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="f7e0a-114">XML Comment Tags</span></span>](index.md)
