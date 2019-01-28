---
title: '&lt;permission&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 5d78261807ab06bd5f89b5438648c5eb0dc56ad9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739458"
---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="fe12e-102">&lt;permission&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fe12e-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="fe12e-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe12e-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe12e-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe12e-104">Parameters</span></span>  
 <span data-ttu-id="fe12e-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="fe12e-105">cref = " `member`"</span></span>  
 <span data-ttu-id="fe12e-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe12e-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="fe12e-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="fe12e-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="fe12e-108">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="fe12e-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="fe12e-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="fe12e-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="fe12e-110">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="fe12e-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe12e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe12e-111">Remarks</span></span>  
 <span data-ttu-id="fe12e-112">Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="fe12e-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="fe12e-113">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="fe12e-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="fe12e-114">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="fe12e-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe12e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe12e-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fe12e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe12e-116">See also</span></span>

- [<span data-ttu-id="fe12e-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fe12e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fe12e-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="fe12e-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
