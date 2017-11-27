---
title: '&lt;umfassen&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="cfa92-102">&lt;umfassen&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfa92-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="cfa92-103">Bezieht sich auf eine andere Datei, die die Typen und Member im Quellcode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="cfa92-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfa92-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfa92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfa92-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="cfa92-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cfa92-106">Required.</span></span> <span data-ttu-id="cfa92-107">Der Name der Datei mit der Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="cfa92-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="cfa92-108">Der Dateiname kann mit einem Pfad qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="cfa92-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="cfa92-109">Schließen Sie `filename` in doppelte Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="cfa92-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="cfa92-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cfa92-110">Required.</span></span> <span data-ttu-id="cfa92-111">Der Pfad der Tags in `filename`, der zum Tag `name` führt.</span><span class="sxs-lookup"><span data-stu-id="cfa92-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="cfa92-112">Schließen Sie den Pfad in doppelte Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="cfa92-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="cfa92-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cfa92-113">Required.</span></span> <span data-ttu-id="cfa92-114">Der Namensbezeichner in dem Tag, das die Kommentare vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="cfa92-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="cfa92-115">`Name`weist ein `id`.</span><span class="sxs-lookup"><span data-stu-id="cfa92-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="cfa92-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cfa92-116">Required.</span></span> <span data-ttu-id="cfa92-117">Die ID für das Tag, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="cfa92-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="cfa92-118">Die ID muss in einfache Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="cfa92-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfa92-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfa92-119">Remarks</span></span>  
 <span data-ttu-id="cfa92-120">Verwenden der `<include>` -Tag zum Verweisen auf Kommentare in einer anderen Datei, die beschreiben, die Typen und Member im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="cfa92-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="cfa92-121">Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="cfa92-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="cfa92-122">Die `<include>` Tag verwendet die Empfehlung der W3C XML Path Language (XPath) Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="cfa92-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="cfa92-123">Weitere Informationen zu Methoden zum Anpassen Ihrer `<include>` Verwendung finden Sie unter http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="cfa92-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa92-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfa92-124">Example</span></span>  
 <span data-ttu-id="cfa92-125">Dieses Beispiel verwendet die `<include>` Tag Dokumentationskommentare Mitglied aus einer Datei namens importieren `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="cfa92-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="cfa92-126">Das Format der `commentFile.xml` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="cfa92-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cfa92-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfa92-127">See Also</span></span>  
 [<span data-ttu-id="cfa92-128">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="cfa92-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
