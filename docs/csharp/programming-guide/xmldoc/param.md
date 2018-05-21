---
title: '&lt;param&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 3d89637e5b1238c582390750e8eef30960fa90b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="8e745-102">&lt;param&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8e745-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8e745-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e745-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e745-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e745-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8e745-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="8e745-105">The name of a method parameter.</span></span> <span data-ttu-id="8e745-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="8e745-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="8e745-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="8e745-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e745-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e745-108">Remarks</span></span>  
 <span data-ttu-id="8e745-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8e745-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="8e745-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="8e745-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="8e745-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e745-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="8e745-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8e745-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e745-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e745-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8e745-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e745-114">See Also</span></span>  
 [<span data-ttu-id="8e745-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8e745-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e745-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="8e745-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
