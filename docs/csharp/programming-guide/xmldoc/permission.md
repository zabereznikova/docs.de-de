---
title: <permission> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 67e9d398d1bb43d480f8ca56733106e0f0a22731
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696570"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="4b787-102">\<permission> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4b787-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4b787-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b787-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b787-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b787-104">Parameters</span></span>  
 <span data-ttu-id="4b787-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="4b787-105">cref = " `member`"</span></span>  
 <span data-ttu-id="4b787-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b787-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4b787-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="4b787-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="4b787-108">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4b787-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="4b787-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="4b787-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="4b787-110">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="4b787-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b787-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b787-111">Remarks</span></span>  
 <span data-ttu-id="4b787-112">Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="4b787-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="4b787-113">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="4b787-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="4b787-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b787-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b787-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b787-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="4b787-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b787-116">See also</span></span>

- [<span data-ttu-id="4b787-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4b787-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4b787-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="4b787-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
