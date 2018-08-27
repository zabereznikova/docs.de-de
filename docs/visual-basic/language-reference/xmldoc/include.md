---
title: '&lt;umfassen&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932963"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="b5c32-102">&lt;umfassen&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5c32-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="b5c32-103">Bezieht sich auf eine andere Datei, die die Typen und Member im Quellcode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b5c32-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5c32-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5c32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5c32-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="b5c32-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5c32-106">Required.</span></span> <span data-ttu-id="b5c32-107">Der Name der Datei, die die Dokumentation enthält.</span><span class="sxs-lookup"><span data-stu-id="b5c32-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="b5c32-108">Der Dateiname kann mit einem Pfad qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="b5c32-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="b5c32-109">Schließen Sie `filename` in doppelte Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="b5c32-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="b5c32-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5c32-110">Required.</span></span> <span data-ttu-id="b5c32-111">Der Pfad der Tags in `filename`, der zum Tag `name` führt.</span><span class="sxs-lookup"><span data-stu-id="b5c32-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="b5c32-112">Schließen Sie den Pfad in doppelte Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="b5c32-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="b5c32-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5c32-113">Required.</span></span> <span data-ttu-id="b5c32-114">Der Namensbezeichner in dem Tag, das vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="b5c32-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="b5c32-115">`Name` hat eine `id`.</span><span class="sxs-lookup"><span data-stu-id="b5c32-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="b5c32-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5c32-116">Required.</span></span> <span data-ttu-id="b5c32-117">Die ID für das Tag, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="b5c32-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="b5c32-118">Die ID muss in einfache Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="b5c32-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5c32-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5c32-119">Remarks</span></span>  
 <span data-ttu-id="b5c32-120">Verwenden der `<include>` -Tag zum Verweisen auf Kommentare in einer anderen Datei, die beschreiben, die Typen und Member im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="b5c32-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="b5c32-121">Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="b5c32-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="b5c32-122">Die `<include>` Tag verwendet die Empfehlung des W3C XML Path Language (XPath) Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="b5c32-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="b5c32-123">Weitere Informationen zu Möglichkeiten zum Anpassen Ihrer `<include>` Verwendung finden Sie unter http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="b5c32-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5c32-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5c32-124">Example</span></span>  
 <span data-ttu-id="b5c32-125">Dieses Beispiel verwendet die `<include>` Tag zum Importieren von Dokumentationskommentaren Member aus einer Datei namens `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="b5c32-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="b5c32-126">Das Format der `commentFile.xml` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="b5c32-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b5c32-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5c32-127">See Also</span></span>  
 [<span data-ttu-id="b5c32-128">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="b5c32-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
