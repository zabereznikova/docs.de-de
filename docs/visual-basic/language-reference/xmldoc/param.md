---
title: '&lt;param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: cc9ceccef8123d49d6267276e9dcb7be84f78a01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670679"
---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="33409-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33409-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="33409-103">Definiert einen Namen und eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="33409-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33409-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33409-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33409-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33409-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="33409-106">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="33409-106">The name of a method parameter.</span></span> <span data-ttu-id="33409-107">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="33409-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="33409-108">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="33409-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33409-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33409-109">Remarks</span></span>  
 <span data-ttu-id="33409-110">Die `<param>` -Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter für die Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="33409-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="33409-111">Der Text für die `<param>` Tag wird in den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="33409-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="33409-112">ParameterInfo von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="33409-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="33409-113">Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="33409-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="33409-114">Objekt-Browser.</span><span class="sxs-lookup"><span data-stu-id="33409-114">Object Browser.</span></span> <span data-ttu-id="33409-115">Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="33409-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="33409-116">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="33409-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33409-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33409-117">Example</span></span>  
 <span data-ttu-id="33409-118">Dieses Beispiel verwendet die `<param>` Tag zum Beschreiben der `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="33409-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="33409-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33409-119">See also</span></span>
- [<span data-ttu-id="33409-120">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="33409-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
