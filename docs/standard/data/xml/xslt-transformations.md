---
title: XSLT-Transformationen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 92d0688b86e6a95af46e09c21c1a8b3cdf66efc3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="xslt-transformations"></a><span data-ttu-id="62bed-102">XSLT-Transformationen</span><span class="sxs-lookup"><span data-stu-id="62bed-102">XSLT Transformations</span></span>
<span data-ttu-id="62bed-103">Mit XSLT (Extensible Stylesheet Language Transformation) können Sie den Inhalt eines XML-Quelldokuments in ein anderes Dokument mit anderem Format oder einer anderen Struktur transformieren.</span><span class="sxs-lookup"><span data-stu-id="62bed-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="62bed-104">Mit XSLT können Sie beispielsweise XML in HTML für eine Website transformieren oder in ein Dokument, das nur die für eine Anwendung erforderlichen Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="62bed-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="62bed-105">Dieser Transformationsprozess wird in der [W3C-Empfehlung zu XSL-Transformationen (XSLT) Version 1.0](http://go.microsoft.com/fwlink/?LinkID=49919) spezifiziert.</span><span class="sxs-lookup"><span data-stu-id="62bed-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](http://go.microsoft.com/fwlink/?LinkID=49919).</span></span>  
  
 <span data-ttu-id="62bed-106">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62bed-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in the .NET Framework.</span></span> <span data-ttu-id="62bed-107">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt die W3C-Empfehlung zu XSLT 1.0.</span><span class="sxs-lookup"><span data-stu-id="62bed-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the W3C XSLT 1.0 recommendation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62bed-108">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="62bed-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="62bed-109">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist eine neue Implementierung des XSLT-Moduls.</span><span class="sxs-lookup"><span data-stu-id="62bed-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="62bed-110">Sie enthält Leistungsverbesserungen und neue Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="62bed-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="62bed-111">Es wird empfohlen, XSLT-Anwendungen mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62bed-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62bed-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62bed-112">In This Section</span></span>  
 [<span data-ttu-id="62bed-113">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="62bed-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="62bed-114">Enthält Informationen zur Verwendung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="62bed-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="62bed-115">Migrieren von der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="62bed-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="62bed-116">Behandelt die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="62bed-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="62bed-117">XSLT-Compiler („xsltc.exe“)</span><span class="sxs-lookup"><span data-stu-id="62bed-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="62bed-118">Enthält Informationen zur Verwendung des XSLT-Compilers.</span><span class="sxs-lookup"><span data-stu-id="62bed-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="62bed-119">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="62bed-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="62bed-120">Enthält Informationen zur Verwendung der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="62bed-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 <span data-ttu-id="62bed-121">**Hinweis** Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="62bed-121">**Note** The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0 release.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="62bed-122">Verweis</span><span class="sxs-lookup"><span data-stu-id="62bed-122">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="62bed-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62bed-123">Related Sections</span></span>  
 [<span data-ttu-id="62bed-124">XML-Dokumente und -Daten</span><span class="sxs-lookup"><span data-stu-id="62bed-124">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
