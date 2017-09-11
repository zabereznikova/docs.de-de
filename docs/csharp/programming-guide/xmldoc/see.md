---
title: '&lt;see&gt; (C# -Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- CSharp
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
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
ms.openlocfilehash: 831caae9574c25f16e8b2ede734746f48019198e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="f7228-102">&lt;see&gt; (C# -Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f7228-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f7228-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7228-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7228-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7228-104">Parameters</span></span>  
 <span data-ttu-id="f7228-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="f7228-105">cref = " `member`"</span></span>  
 <span data-ttu-id="f7228-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7228-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="f7228-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. *member* muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f7228-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7228-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7228-108">Remarks</span></span>  
 <span data-ttu-id="f7228-109">Mit dem \<see>-Tag kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7228-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="f7228-110">Verwenden Sie [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7228-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="f7228-111">Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7228-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="f7228-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="f7228-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="f7228-113">Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7228-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 <span data-ttu-id="f7228-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7228-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7228-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7228-115">See Also</span></span>  
 <span data-ttu-id="f7228-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7228-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f7228-117">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="f7228-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

