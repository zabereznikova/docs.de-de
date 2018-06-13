---
title: '&lt;seealso&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e3c9d68884e5cd4f5a4f81580f60cdde775458a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349134"
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="ba372-102">&lt;seealso&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ba372-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ba372-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba372-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba372-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba372-104">Parameters</span></span>  
 <span data-ttu-id="ba372-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="ba372-105">cref = " `member`"</span></span>  
 <span data-ttu-id="ba372-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba372-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ba372-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="ba372-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="ba372-108">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ba372-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="ba372-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="ba372-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba372-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba372-110">Remarks</span></span>  
 <span data-ttu-id="ba372-111">Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba372-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="ba372-112">Mit [\<see>](../../../csharp/programming-guide/xmldoc/see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ba372-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="ba372-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ba372-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba372-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba372-114">Example</span></span>  
 <span data-ttu-id="ba372-115">Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="ba372-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba372-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba372-116">See Also</span></span>  
 [<span data-ttu-id="ba372-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ba372-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ba372-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="ba372-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
