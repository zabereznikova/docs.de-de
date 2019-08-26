---
title: <seealso> – C#-Programmierhandbuch
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
ms.openlocfilehash: 3ddaa7efec2b4bf5ffa53971aa6f380a1be9bad8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587659"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="a6650-102">\<seealso> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a6650-102">\<seealso> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a6650-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6650-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6650-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6650-104">Parameters</span></span>  
 <span data-ttu-id="a6650-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="a6650-105">cref = " `member`"</span></span>  
 <span data-ttu-id="a6650-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a6650-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="a6650-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="a6650-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="a6650-108">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a6650-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="a6650-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="a6650-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6650-110">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a6650-110">Remarks</span></span>  
 <span data-ttu-id="a6650-111">Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a6650-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="a6650-112">Mit [\<see>](./see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6650-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="a6650-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a6650-113">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6650-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6650-114">Example</span></span>  
 <span data-ttu-id="a6650-115">Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="a6650-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6650-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6650-116">See also</span></span>

- [<span data-ttu-id="a6650-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a6650-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a6650-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a6650-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
