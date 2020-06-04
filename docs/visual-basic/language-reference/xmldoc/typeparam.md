---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411485"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="d182d-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d182d-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="d182d-102">Definiert einen Typparameter Namen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="d182d-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d182d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="d182d-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d182d-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="d182d-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d182d-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="d182d-105">The name of the type parameter.</span></span> <span data-ttu-id="d182d-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="d182d-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d182d-107">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="d182d-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d182d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d182d-108">Remarks</span></span>  
 <span data-ttu-id="d182d-109">Verwenden Sie das- `<typeparam>` Tag im Kommentar für einen generischen Typ oder eine generische Element Deklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d182d-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="d182d-110">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d182d-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d182d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d182d-111">Example</span></span>  
 <span data-ttu-id="d182d-112">In diesem Beispiel wird das- `<typeparam>` Tag zum Beschreiben des- `id` Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="d182d-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="d182d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d182d-113">See also</span></span>

- [<span data-ttu-id="d182d-114">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d182d-114">XML Comment Tags</span></span>](index.md)
