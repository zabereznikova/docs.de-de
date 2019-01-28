---
title: '&lt;typeparam&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 21819bebbb304eaace3950f40b97033762cd6ce8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568048"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="d9d28-102">&lt;typeparam&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d9d28-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d9d28-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9d28-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9d28-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9d28-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d9d28-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="d9d28-105">The name of the type parameter.</span></span> <span data-ttu-id="d9d28-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="d9d28-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d9d28-107">Eine Beschreibung für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="d9d28-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d28-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9d28-108">Remarks</span></span>  
 <span data-ttu-id="d9d28-109">Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d9d28-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="d9d28-110">Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="d9d28-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="d9d28-111">Weitere Informationen finden Sie unter [Generika](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="d9d28-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="d9d28-112">Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.</span><span class="sxs-lookup"><span data-stu-id="d9d28-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="d9d28-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="d9d28-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9d28-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9d28-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d9d28-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d28-115">See also</span></span>

- [<span data-ttu-id="d9d28-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d9d28-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d9d28-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d9d28-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d9d28-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="d9d28-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
