---
title: '&lt;seealso&gt; (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cref
- <seealso>
- seealso
dev_langs:
- CSharp
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: 11
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
ms.openlocfilehash: 7b4686ba83d2caedcc6c93ad8877d1da671d10d4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="2a409-102">&lt;seealso&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2a409-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2a409-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a409-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a409-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a409-104">Parameters</span></span>  
 <span data-ttu-id="2a409-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="2a409-105">cref = " `member`"</span></span>  
 <span data-ttu-id="2a409-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a409-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2a409-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="2a409-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="2a409-108">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2a409-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="2a409-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="2a409-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a409-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a409-110">Remarks</span></span>  
 <span data-ttu-id="2a409-111">Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2a409-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="2a409-112">Mit [\<see>](../../../csharp/programming-guide/xmldoc/see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a409-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="2a409-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="2a409-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a409-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a409-114">Example</span></span>  
 <span data-ttu-id="2a409-115">Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="2a409-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a409-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a409-116">See Also</span></span>  
 <span data-ttu-id="2a409-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a409-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2a409-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="2a409-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

