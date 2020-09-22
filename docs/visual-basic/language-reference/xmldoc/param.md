---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 19300a928a59c7259f81b282bd28d9bdd447d76b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872623"
---
# <a name="param-visual-basic"></a><span data-ttu-id="ebef2-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebef2-101">\<param> (Visual Basic)</span></span>

<span data-ttu-id="ebef2-102">Definiert einen Parameternamen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="ebef2-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebef2-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebef2-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebef2-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebef2-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="ebef2-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="ebef2-105">The name of a method parameter.</span></span> <span data-ttu-id="ebef2-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="ebef2-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ebef2-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="ebef2-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebef2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebef2-108">Remarks</span></span>  

 <span data-ttu-id="ebef2-109">Das `<param>`-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ebef2-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="ebef2-110">Der Text für das `<param>` Tag wird an den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ebef2-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="ebef2-111">Parameter Informationen von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ebef2-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="ebef2-112">Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="ebef2-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="ebef2-113">Objektkatalog.</span><span class="sxs-lookup"><span data-stu-id="ebef2-113">Object Browser.</span></span> <span data-ttu-id="ebef2-114">Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="ebef2-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="ebef2-115">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebef2-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebef2-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebef2-116">Example</span></span>  

 <span data-ttu-id="ebef2-117">In diesem Beispiel wird das- `<param>` Tag zum Beschreiben des- `id` Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebef2-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ebef2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebef2-118">See also</span></span>

- [<span data-ttu-id="ebef2-119">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="ebef2-119">XML Comment Tags</span></span>](index.md)
