---
title: <typeparam> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 04145b82cbed0e9a5cae38ff9ef33d061ee792c9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694529"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="f88d1-102">\<typeparam> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f88d1-102">\<typeparam> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f88d1-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f88d1-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f88d1-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="f88d1-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f88d1-105">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="f88d1-105">The name of the type parameter.</span></span> <span data-ttu-id="f88d1-106">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="f88d1-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f88d1-107">Eine Beschreibung für den Typparameter.</span><span class="sxs-lookup"><span data-stu-id="f88d1-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f88d1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f88d1-108">Remarks</span></span>  
 <span data-ttu-id="f88d1-109">Die `<typeparam>` -Tag sollte im Kommentar für einen generischen Typ oder eine Methodendeklaration verwendet werden, um einen Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f88d1-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="f88d1-110">Fügen Sie ein Tag für jeden Typparameter des generischen Typs oder der Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f88d1-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="f88d1-111">Weitere Informationen finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f88d1-111">For more information, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="f88d1-112">Der Text für die `<typeparam>` Tag wird in IntelliSense angezeigt werden, dem [Objekt Browserfenster](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) Webbericht für Codekommentare.</span><span class="sxs-lookup"><span data-stu-id="f88d1-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="f88d1-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f88d1-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f88d1-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f88d1-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="f88d1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f88d1-115">See also</span></span>

- [<span data-ttu-id="f88d1-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f88d1-116">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="f88d1-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f88d1-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f88d1-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="f88d1-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
