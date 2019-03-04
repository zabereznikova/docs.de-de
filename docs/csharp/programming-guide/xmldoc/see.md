---
title: <see> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1816aeb0ddf783c8ad0baa7f5d460f0fc60747e1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974821"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="906cb-102">\<see> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="906cb-102">\<see> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="906cb-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="906cb-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="906cb-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="906cb-104">Parameters</span></span>  
 <span data-ttu-id="906cb-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="906cb-105">cref = " `member`"</span></span>  
 <span data-ttu-id="906cb-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="906cb-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="906cb-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="906cb-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="906cb-108">Setzen Sie *member* in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="906cb-108">Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="906cb-109">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="906cb-109">Remarks</span></span>  
 <span data-ttu-id="906cb-110">Mit dem \<see>-Tag kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="906cb-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="906cb-111">Verwenden Sie [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="906cb-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="906cb-112">Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="906cb-112">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="906cb-113">Kompilieren Sie mit [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="906cb-113">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="906cb-114">Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="906cb-114">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="906cb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="906cb-115">See also</span></span>

- [<span data-ttu-id="906cb-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="906cb-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="906cb-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="906cb-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
