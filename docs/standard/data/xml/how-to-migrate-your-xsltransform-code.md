---
title: "Vorgehensweise: Migrieren des 'XslTransform'-Codes"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
ms.openlocfilehash: 2bc5cbc1b0857a82d3b0a11f05a4eb5756724546
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710842"
---
# <a name="how-to-migrate-your-xsltransform-code"></a><span data-ttu-id="7b89f-102">Vorgehensweise: Migrieren des 'XslTransform'-Codes</span><span class="sxs-lookup"><span data-stu-id="7b89f-102">How to: Migrate Your XslTransform Code</span></span>
<span data-ttu-id="7b89f-103">Die neuen XSLT-Klassen entsprechen weitgehend den bereits vorhandenen Klassen.</span><span class="sxs-lookup"><span data-stu-id="7b89f-103">The new XSLT classes have been designed to be very similar to the existing classes.</span></span> <span data-ttu-id="7b89f-104">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ersetzt die <xref:System.Xml.Xsl.XslTransform>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="7b89f-104">The <xref:System.Xml.Xsl.XslCompiledTransform> class replaces the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="7b89f-105">Stylesheets werden mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode kompiliert.</span><span class="sxs-lookup"><span data-stu-id="7b89f-105">Style sheets are compiled using the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="7b89f-106">Transformationen erfolgen mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="7b89f-106">Transforms are executed using the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="7b89f-107">In den folgenden Verfahren werden allgemeine XSLT-Aufgaben veranschaulicht, und der Code wird anhand der <xref:System.Xml.Xsl.XslTransform>-Klasse und der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse verglichen.</span><span class="sxs-lookup"><span data-stu-id="7b89f-107">The following procedures show common XSLT tasks, and compare the code using the <xref:System.Xml.Xsl.XslTransform> class versus the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a><span data-ttu-id="7b89f-108">So transformieren Sie eine Datei und geben sie an einen URI aus</span><span class="sxs-lookup"><span data-stu-id="7b89f-108">To transform a file and output to a URI</span></span>  
  
- <span data-ttu-id="7b89f-109">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-109">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
- <span data-ttu-id="7b89f-110">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-110">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a><span data-ttu-id="7b89f-111">So kompilieren Sie ein Stylesheet und verwenden einen Resolver mit Standardanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="7b89f-111">To compile a style sheet and use a resolver with default credentials</span></span>  
  
- <span data-ttu-id="7b89f-112">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-112">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
- <span data-ttu-id="7b89f-113">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-113">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="7b89f-114">So verwenden Sie einen XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="7b89f-114">To use an XSLT parameter</span></span>  
  
- <span data-ttu-id="7b89f-115">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-115">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
- <span data-ttu-id="7b89f-116">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-116">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a><span data-ttu-id="7b89f-117">So aktivieren Sie die XSLT-Skripterstellung</span><span class="sxs-lookup"><span data-stu-id="7b89f-117">To enable XSLT scripting</span></span>  
  
- <span data-ttu-id="7b89f-118">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-118">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
- <span data-ttu-id="7b89f-119">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-119">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a><span data-ttu-id="7b89f-120">So laden Sie die Ergebnisse in ein DOM-Objekt</span><span class="sxs-lookup"><span data-stu-id="7b89f-120">To load the results into a DOM object</span></span>  
  
- <span data-ttu-id="7b89f-121">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-121">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
- <span data-ttu-id="7b89f-122">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-122">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7b89f-123">Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse weist keine Methode auf, die die Ergebnisse der XSLT-Transformationen als <xref:System.Xml.XmlReader>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7b89f-123">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have a method that returns the XSLT transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="7b89f-124">Sie können diese jedoch in eine XML-Datei ausgeben und diese XML-Datei in ein anderes Objekt laden.</span><span class="sxs-lookup"><span data-stu-id="7b89f-124">However, you can output to an XML file and load the XML file into another object.</span></span>  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a><span data-ttu-id="7b89f-125">So geben Sie die Ergebnisse in einem Datenstream in einen anderen Datenspeicher aus</span><span class="sxs-lookup"><span data-stu-id="7b89f-125">To stream the results into another data store</span></span>  
  
- <span data-ttu-id="7b89f-126">Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-126">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
- <span data-ttu-id="7b89f-127">Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b89f-127">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="7b89f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b89f-128">See also</span></span>

- [<span data-ttu-id="7b89f-129">Migrieren von der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="7b89f-129">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)
- [<span data-ttu-id="7b89f-130">Verwenden der XslCompiledTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="7b89f-130">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
