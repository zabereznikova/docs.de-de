---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400059"
---
# <a name="param-visual-basic"></a><span data-ttu-id="97de3-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97de3-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="97de3-102">Definiert einen Parameternamen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="97de3-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97de3-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="97de3-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="97de3-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="97de3-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="97de3-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="97de3-105">The name of a method parameter.</span></span> <span data-ttu-id="97de3-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="97de3-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="97de3-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="97de3-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97de3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97de3-108">Remarks</span></span>  
 <span data-ttu-id="97de3-109">Das- `<param>` Tag sollte im Kommentar für eine Methoden Deklaration verwendet werden, um einen der Parameter für die-Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="97de3-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="97de3-110">Der Text für das `<param>` Tag wird an den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="97de3-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="97de3-111">Parameter Informationen von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="97de3-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="97de3-112">Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="97de3-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="97de3-113">Objektkatalog.</span><span class="sxs-lookup"><span data-stu-id="97de3-113">Object Browser.</span></span> <span data-ttu-id="97de3-114">Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="97de3-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="97de3-115">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md) , um Dokumentations Kommentare in einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="97de3-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97de3-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97de3-116">Example</span></span>  
 <span data-ttu-id="97de3-117">In diesem Beispiel wird das- `<param>` Tag zum Beschreiben des- `id` Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="97de3-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="97de3-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97de3-118">See also</span></span>

- [<span data-ttu-id="97de3-119">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="97de3-119">XML Comment Tags</span></span>](index.md)
