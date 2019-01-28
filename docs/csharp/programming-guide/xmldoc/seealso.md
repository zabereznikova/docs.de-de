---
title: '&lt;seealso&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
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
ms.openlocfilehash: e75480db9aebdeb2199694168abf4f774773b9c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543551"
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="94ea5-102">&lt;seealso&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="94ea5-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="94ea5-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="94ea5-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94ea5-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="94ea5-104">Parameters</span></span>  
 <span data-ttu-id="94ea5-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="94ea5-105">cref = " `member`"</span></span>  
 <span data-ttu-id="94ea5-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="94ea5-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="94ea5-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="94ea5-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="94ea5-108">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="94ea5-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="94ea5-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="94ea5-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94ea5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94ea5-110">Remarks</span></span>  
 <span data-ttu-id="94ea5-111">Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="94ea5-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="94ea5-112">Mit [\<see>](../../../csharp/programming-guide/xmldoc/see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="94ea5-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="94ea5-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="94ea5-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ea5-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94ea5-114">Example</span></span>  
 <span data-ttu-id="94ea5-115">Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="94ea5-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ea5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94ea5-116">See also</span></span>

- [<span data-ttu-id="94ea5-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="94ea5-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="94ea5-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="94ea5-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
