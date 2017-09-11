---
title: '&lt;Param&gt; (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: ddf5baf83816d757edf67cdf1c66dc24e4313b83
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="4f80c-102">&lt;Param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f80c-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="4f80c-103">Definiert einen Parametername und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="4f80c-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f80c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f80c-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f80c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f80c-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4f80c-106">Der Name des Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="4f80c-106">The name of a method parameter.</span></span> <span data-ttu-id="4f80c-107">Der Name muss in doppelte Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="4f80c-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="4f80c-108">Eine Beschreibung für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="4f80c-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f80c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f80c-109">Remarks</span></span>  
 <span data-ttu-id="4f80c-110">Der `<param>` -Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter der Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4f80c-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="4f80c-111">Der Text für die `<param>` Tag wird in den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4f80c-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="4f80c-112">ParameterInfo von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4f80c-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="4f80c-113">Weitere Informationen finden Sie unter [Verwenden von IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="4f80c-113">For more information, see [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="4f80c-114">Objektkatalog.</span><span class="sxs-lookup"><span data-stu-id="4f80c-114">Object Browser.</span></span> <span data-ttu-id="4f80c-115">Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)..</span><span class="sxs-lookup"><span data-stu-id="4f80c-115">For more information, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="4f80c-116">Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="4f80c-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f80c-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f80c-117">Example</span></span>  
 <span data-ttu-id="4f80c-118">Dieses Beispiel verwendet die `<param>` Tag beschreiben die `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="4f80c-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 <span data-ttu-id="4f80c-119">[!code-vb[VbVbcnXmlDocComments&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f80c-119">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f80c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f80c-120">See Also</span></span>  
 [<span data-ttu-id="4f80c-121">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4f80c-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
