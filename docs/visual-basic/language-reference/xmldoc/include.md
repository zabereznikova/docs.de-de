---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400110"
---
# <a name="include-visual-basic"></a><span data-ttu-id="fcaf4-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcaf4-101">\<include> (Visual Basic)</span></span>
<span data-ttu-id="fcaf4-102">Verweist auf eine andere Datei, in der die Typen und Member im Quellcode beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcaf4-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcaf4-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcaf4-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcaf4-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="fcaf4-105">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-105">Required.</span></span> <span data-ttu-id="fcaf4-106">Der Name der Datei, die die Dokumentation enthält.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="fcaf4-107">Der Dateiname kann mit einem Pfad qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="fcaf4-108">Schließen Sie `filename` in doppelte Anführungszeichen ("") ein.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="fcaf4-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-109">Required.</span></span> <span data-ttu-id="fcaf4-110">Der Pfad der Tags in `filename`, der zum Tag `name` führt.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="fcaf4-111">Schließen Sie den Pfad in doppelte Anführungszeichen ("") ein.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="fcaf4-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-112">Required.</span></span> <span data-ttu-id="fcaf4-113">Der namensspezifizierer im-Tag, der den Kommentaren vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="fcaf4-114">`Name`verfügt über einen `id` .</span><span class="sxs-lookup"><span data-stu-id="fcaf4-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="fcaf4-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-115">Required.</span></span> <span data-ttu-id="fcaf4-116">Die ID für das Tag, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="fcaf4-117">Schließen Sie die ID in einfache Anführungszeichen (' ') ein.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcaf4-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fcaf4-118">Remarks</span></span>  
 <span data-ttu-id="fcaf4-119">Verwenden Sie das- `<include>` Tag, um auf Kommentare in einer anderen Datei zu verweisen, die die Typen und Member im Quellcode beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="fcaf4-120">Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="fcaf4-121">Das- `<include>` Tag verwendet die W3C-Empfehlung XPath (XML Path Language), Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="fcaf4-122">Weitere Informationen zu Möglichkeiten zum Anpassen Ihrer `<include>` Verwendung finden Sie unter <https://www.w3.org/TR/xpath> .</span><span class="sxs-lookup"><span data-stu-id="fcaf4-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcaf4-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcaf4-123">Example</span></span>  
 <span data-ttu-id="fcaf4-124">In diesem Beispiel wird das- `<include>` Tag verwendet, um Member-Dokumentations Kommentare aus einer Datei namens zu importieren `commentFile.xml` .</span><span class="sxs-lookup"><span data-stu-id="fcaf4-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="fcaf4-125">Das Format von `commentFile.xml` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fcaf4-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcaf4-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcaf4-126">See also</span></span>

- [<span data-ttu-id="fcaf4-127">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="fcaf4-127">XML Comment Tags</span></span>](index.md)
