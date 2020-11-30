---
title: XSLT-Transformationen
ms.date: 03/30/2017
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
ms.openlocfilehash: 686b2d454eda99095bcb335c8b0edba9ecf2e304
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685057"
---
# <a name="xslt-transformations"></a><span data-ttu-id="e7b8b-102">XSLT-Transformationen</span><span class="sxs-lookup"><span data-stu-id="e7b8b-102">XSLT Transformations</span></span>

<span data-ttu-id="e7b8b-103">Mit XSLT (Extensible Stylesheet Language Transformation) können Sie den Inhalt eines XML-Quelldokuments in ein anderes Dokument mit anderem Format oder einer anderen Struktur transformieren.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="e7b8b-104">Mit XSLT können Sie beispielsweise XML in HTML für eine Website transformieren oder in ein Dokument, das nur die für eine Anwendung erforderlichen Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="e7b8b-105">Dieser Transformationsprozess wird in der [W3C-Empfehlung zu XSL-Transformationen (XSLT) Version 1.0](https://www.w3.org/TR/xslt-10/) spezifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
 <span data-ttu-id="e7b8b-106">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist der XSLT-Prozessor in .NET.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in .NET.</span></span> <span data-ttu-id="e7b8b-107">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt die [W3C-Empfehlung zu XSLT 1.0](https://www.w3.org/TR/xslt-10/).</span><span class="sxs-lookup"><span data-stu-id="e7b8b-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the [W3C XSLT 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7b8b-108">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="e7b8b-109">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ist eine neue Implementierung der XSLT-Engine.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="e7b8b-110">Sie enthält Leistungsverbesserungen und neue Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="e7b8b-111">Es wird empfohlen, XSLT-Anwendungen mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7b8b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e7b8b-112">In This Section</span></span>  

 [<span data-ttu-id="e7b8b-113">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="e7b8b-113">Using the XslCompiledTransform Class</span></span>](using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="e7b8b-114">Enthält Informationen zur Verwendung der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="e7b8b-115">Migrieren von der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="e7b8b-115">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="e7b8b-116">Behandelt die Migration von Code von der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="e7b8b-117">XSLT-Compiler („xsltc.exe“)</span><span class="sxs-lookup"><span data-stu-id="e7b8b-117">XSLT Compiler (xsltc.exe)</span></span>](xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="e7b8b-118">Enthält Informationen zur Verwendung des XSLT-Compilers.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="e7b8b-119">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="e7b8b-119">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="e7b8b-120">Enthält Informationen zur Verwendung der <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e7b8b-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e7b8b-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="e7b8b-121">Reference</span></span>  

 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="e7b8b-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e7b8b-122">Related Sections</span></span>  

 [<span data-ttu-id="e7b8b-123">XML-Dokumente und -Daten</span><span class="sxs-lookup"><span data-stu-id="e7b8b-123">XML Documents and Data</span></span>](index.md)
