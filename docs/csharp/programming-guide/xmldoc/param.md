---
title: '&lt;param&gt; (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs:
- CSharp
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1076405d60c85540eeaeba39821bd20bc628030d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="9ddb0-102">&lt;param&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9ddb0-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9ddb0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ddb0-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ddb0-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ddb0-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9ddb0-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="9ddb0-105">The name of a method parameter.</span></span> <span data-ttu-id="9ddb0-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="9ddb0-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9ddb0-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="9ddb0-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ddb0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ddb0-108">Remarks</span></span>  
 <span data-ttu-id="9ddb0-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9ddb0-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="9ddb0-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="9ddb0-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="9ddb0-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ddb0-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="9ddb0-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="9ddb0-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ddb0-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9ddb0-113">Example</span></span>  
 <span data-ttu-id="9ddb0-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9ddb0-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddb0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ddb0-115">See Also</span></span>  
 <span data-ttu-id="9ddb0-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ddb0-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9ddb0-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="9ddb0-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

