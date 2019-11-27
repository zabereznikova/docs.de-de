---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352296"
---
# <a name="param-visual-basic"></a><span data-ttu-id="08a46-101">\<param-> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08a46-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="08a46-102">Definiert einen Parameternamen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="08a46-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a46-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="08a46-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a46-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="08a46-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="08a46-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="08a46-105">The name of a method parameter.</span></span> <span data-ttu-id="08a46-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="08a46-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="08a46-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="08a46-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08a46-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08a46-108">Remarks</span></span>  
 <span data-ttu-id="08a46-109">Das `<param>`-Tag sollte im Kommentar für eine Methoden Deklaration verwendet werden, um einen der Parameter für die-Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="08a46-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="08a46-110">Der Text für das `<param>`-Tag wird an den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="08a46-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="08a46-111">Parameter Informationen von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="08a46-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="08a46-112">Weitere Informationen finden Sie unter [Using IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="08a46-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="08a46-113">Objektkatalog.</span><span class="sxs-lookup"><span data-stu-id="08a46-113">Object Browser.</span></span> <span data-ttu-id="08a46-114">Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="08a46-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="08a46-115">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="08a46-115">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08a46-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08a46-116">Example</span></span>  
 <span data-ttu-id="08a46-117">In diesem Beispiel wird das `<param>`-Tag verwendet, um den `id`-Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="08a46-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="08a46-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08a46-118">See also</span></span>

- [<span data-ttu-id="08a46-119">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="08a46-119">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
