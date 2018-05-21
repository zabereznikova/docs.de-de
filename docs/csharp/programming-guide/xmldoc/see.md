---
title: '&lt;see&gt; (C# -Programmierhandbuch)'
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
ms.openlocfilehash: 24fa317a0f89568d9aa1b53849e327ef7615cc7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="a80f7-102">&lt;see&gt; (C# -Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a80f7-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a80f7-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a80f7-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a80f7-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="a80f7-104">Parameters</span></span>  
 <span data-ttu-id="a80f7-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="a80f7-105">cref = " `member`"</span></span>  
 <span data-ttu-id="a80f7-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a80f7-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="a80f7-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. *member* muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a80f7-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a80f7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a80f7-108">Remarks</span></span>  
 <span data-ttu-id="a80f7-109">Mit dem \<see>-Tag kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a80f7-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="a80f7-110">Verwenden Sie [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a80f7-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="a80f7-111">Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a80f7-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="a80f7-112">Kompilieren Sie mit [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a80f7-112">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="a80f7-113">Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a80f7-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a80f7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a80f7-114">See Also</span></span>  
 [<span data-ttu-id="a80f7-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a80f7-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a80f7-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a80f7-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
