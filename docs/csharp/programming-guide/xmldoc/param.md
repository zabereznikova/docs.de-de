---
title: '&lt;param&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: fca53a3cd5490c28c8fabcf69446fe4a55d60b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236959"
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="94856-102">&lt;param&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="94856-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="94856-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="94856-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94856-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="94856-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="94856-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="94856-105">The name of a method parameter.</span></span> <span data-ttu-id="94856-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="94856-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="94856-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="94856-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94856-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94856-108">Remarks</span></span>  
 <span data-ttu-id="94856-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="94856-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="94856-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="94856-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="94856-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94856-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="94856-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="94856-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94856-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94856-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="94856-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94856-114">See Also</span></span>

- [<span data-ttu-id="94856-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="94856-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="94856-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="94856-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
