---
title: <param> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: ed7a8f8a06771a18dc4244bffbda53e9adbd4e90
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523414"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="36a62-102">\<param> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="36a62-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="36a62-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="36a62-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="36a62-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="36a62-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="36a62-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="36a62-105">The name of a method parameter.</span></span> <span data-ttu-id="36a62-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="36a62-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="36a62-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="36a62-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36a62-108">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="36a62-108">Remarks</span></span>  
 <span data-ttu-id="36a62-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="36a62-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="36a62-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="36a62-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="36a62-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36a62-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="36a62-112">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="36a62-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36a62-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36a62-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="36a62-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a62-114">See also</span></span>

- [<span data-ttu-id="36a62-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="36a62-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="36a62-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="36a62-116">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
