---
title: 'Vorgehensweise: Verfügbarmachen eines Feeds als Atom und RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 1b03434e4f9552b714b40d54ba36c8468d0e2ccd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265361"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a><span data-ttu-id="1cd31-102">Vorgehensweise: Verfügbarmachen eines Feeds als Atom und RSS</span><span class="sxs-lookup"><span data-stu-id="1cd31-102">How to: Expose a Feed as Both Atom and RSS</span></span>

<span data-ttu-id="1cd31-103">Windows Communication Foundation (WCF) ermöglicht es Ihnen, einen Dienst zu erstellen, der einen Syndizierungs Feed verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1cd31-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="1cd31-104">In diesem Thema wird erläutert, wie Sie einen Syndication-Dienst erstellen, der Syndication-Feeds sowohl mit Atom 1.0 als auch mit RSS 2.0 verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1cd31-104">This topic discusses how to create a syndication service that exposes a syndication feed using both Atom 1.0 and RSS 2.0.</span></span> <span data-ttu-id="1cd31-105">Dieser Dienst macht einen Endpunkt verfügbar, der beide Syndication-Formate zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="1cd31-105">This service exposes one endpoint that can return either syndication format.</span></span> <span data-ttu-id="1cd31-106">Der Einfachheit halber wird in diesem Beispiel ein selbst gehosteter Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cd31-106">For simplicity the service used in this sample is self hosted.</span></span> <span data-ttu-id="1cd31-107">In einer Produktionsumgebung würde ein Dienst dieses Typs unter IIS oder WAS gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd31-107">In a production environment a service of this type would be hosted under IIS or WAS.</span></span> <span data-ttu-id="1cd31-108">Weitere Informationen zu den verschiedenen WCF-Hostingoptionen finden Sie unter [Hosting](hosting.md).</span><span class="sxs-lookup"><span data-stu-id="1cd31-108">For more information about the different WCF hosting options, see [Hosting](hosting.md).</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="1cd31-109">So erstellen Sie einen grundlegenden Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="1cd31-109">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="1cd31-110">Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="1cd31-110">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="1cd31-111">Jeder Vorgang, der als Syndication-Feed verfügbar gemacht wird, gibt ein <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="1cd31-111">Each operation that is exposed as a syndication feed returns a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> object.</span></span> <span data-ttu-id="1cd31-112">Beachten Sie die Parameter für das <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1cd31-112">Note the parameters for the <xref:System.ServiceModel.Web.WebGetAttribute>.</span></span> <span data-ttu-id="1cd31-113">`UriTemplate` gibt die URL an, mit der dieser Dienstvorgang aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1cd31-113">`UriTemplate` specifies the URL used to invoke this service operation.</span></span> <span data-ttu-id="1cd31-114">Die Zeichenfolge für diesen Parameter enthält Literale und eine Variable in geschweiften Klammern ({*Format*}).</span><span class="sxs-lookup"><span data-stu-id="1cd31-114">The string for this parameter contains literals and a variable in braces ({*format*}).</span></span> <span data-ttu-id="1cd31-115">Diese Variable entspricht dem `format`-Parameter des Dienstvorgangs.</span><span class="sxs-lookup"><span data-stu-id="1cd31-115">This variable corresponds to the service operation's `format` parameter.</span></span> <span data-ttu-id="1cd31-116">Weitere Informationen finden Sie unter <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="1cd31-116">For more information, see <xref:System.UriTemplate>.</span></span> <span data-ttu-id="1cd31-117">`BodyStyle` wirkt sich darauf aus, wie die Nachrichten, die dieser Dienstvorgang sendet und empfängt, geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd31-117">`BodyStyle` affects how the messages that this service operation sends and receives are written.</span></span> <span data-ttu-id="1cd31-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> gibt an, dass die an diesen Dienstvorgang gesendeten und von ihm empfangenen Daten nicht von Infrastruktur-definierten XML-Elementen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1cd31-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> specifies that the data sent to and from this service operation are not wrapped by infrastructure-defined XML elements.</span></span> <span data-ttu-id="1cd31-119">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span><span class="sxs-lookup"><span data-stu-id="1cd31-119">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span></span>  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="1cd31-120">Verwenden Sie das <xref:System.ServiceModel.ServiceKnownTypeAttribute>, um die Typen anzugeben, die von den Dienstvorgängen in dieser Schnittstelle zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1cd31-120">Use the <xref:System.ServiceModel.ServiceKnownTypeAttribute> to specify the types that are returned by the service operations in this interface.</span></span>  
  
2. <span data-ttu-id="1cd31-121">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="1cd31-121">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3. <span data-ttu-id="1cd31-122">Erstellen Sie ein <xref:System.ServiceModel.Syndication.SyndicationFeed>-Objekt, und fügen Sie einen Autor, eine Kategorie und eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cd31-122">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4. <span data-ttu-id="1cd31-123">Erstellen Sie mehrere <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="1cd31-123">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5. <span data-ttu-id="1cd31-124">Fügen Sie die <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte dem Feed hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cd31-124">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6. <span data-ttu-id="1cd31-125">Verwenden Sie den format-Parameter, um das angeforderte Format zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cd31-125">Use the format parameter to return the requested format.</span></span>  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="1cd31-126">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="1cd31-126">To host the service</span></span>  
  
1. <span data-ttu-id="1cd31-127">Erstellen eines <xref:System.ServiceModel.Web.WebServiceHost>-Objekts</span><span class="sxs-lookup"><span data-stu-id="1cd31-127">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span> <span data-ttu-id="1cd31-128">Die <xref:System.ServiceModel.Web.WebServiceHost>-Klasse fügt automatisch einen Endpunkt an der Basisadresse des Diensts hinzu, sofern im Code oder in der Konfiguration kein Endpunkt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1cd31-128">The <xref:System.ServiceModel.Web.WebServiceHost> class automatically adds an endpoint at the service's base address unless one is specified in code or configuration.</span></span> <span data-ttu-id="1cd31-129">In diesem Beispiel sind keine Endpunkte angegeben, sodass der Standardendpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="1cd31-129">In this sample, no endpoints are specified so the default endpoint is exposed.</span></span>  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2. <span data-ttu-id="1cd31-130">Öffnen Sie den Diensthost, laden Sie den Feed vom Dienst, zeigen Sie den Feed an, und warten Sie darauf, dass der Benutzer die Eingabetaste drückt.</span><span class="sxs-lookup"><span data-stu-id="1cd31-130">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="1cd31-131">So rufen Sie GetBlog mit HTTP GET auf</span><span class="sxs-lookup"><span data-stu-id="1cd31-131">To call GetBlog with an HTTP GET</span></span>  
  
1. <span data-ttu-id="1cd31-132">Öffnen Sie Internet Explorer, geben Sie die folgende URL ein, und drücken Sie die EINGABETASTE: `http://localhost:8000/BlogService/GetBlog` .</span><span class="sxs-lookup"><span data-stu-id="1cd31-132">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span>
  
     <span data-ttu-id="1cd31-133">Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/BlogService` ), die relative Adresse des Endpunkts und den aufzurufenden Dienst Vorgang.</span><span class="sxs-lookup"><span data-stu-id="1cd31-133">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="1cd31-134">So rufen Sie GetBlog() aus dem Code auf</span><span class="sxs-lookup"><span data-stu-id="1cd31-134">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="1cd31-135">Erstellen Sie einen <xref:System.Xml.XmlReader> mit der Basisadresse und der Methode, die Sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1cd31-135">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="1cd31-136">Rufen Sie die statische <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>-Methode auf, und übergeben Sie dabei den gerade erstellten <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="1cd31-136">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     <span data-ttu-id="1cd31-137">Dies ruft einen Dienstvorgang auf und füllt einen neuen <xref:System.ServiceModel.Syndication.SyndicationFeed> mit dem vom Dienstvorgang zurückgegebenen Formatierungsprogramm auf.</span><span class="sxs-lookup"><span data-stu-id="1cd31-137">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="1cd31-138">Greifen Sie auf das Feedobjekt zu.</span><span class="sxs-lookup"><span data-stu-id="1cd31-138">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="1cd31-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1cd31-139">Example</span></span>  

 <span data-ttu-id="1cd31-140">Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="1cd31-140">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1cd31-141">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1cd31-141">Compiling the Code</span></span>  

 <span data-ttu-id="1cd31-142">Verweisen Sie beim Kompilieren des obigen Codes auf System.ServiceModel.dll und System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="1cd31-142">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd31-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cd31-143">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
