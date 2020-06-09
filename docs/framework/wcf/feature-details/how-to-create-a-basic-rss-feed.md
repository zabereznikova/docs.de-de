---
title: 'Vorgehensweise: Erstellen eines grundlegenden RSS-Feeds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: 872fe325a6705e79d026cd7f6e1f7cfef5145307
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599021"
---
# <a name="how-to-create-a-basic-rss-feed"></a><span data-ttu-id="55cbb-102">Vorgehensweise: Erstellen eines grundlegenden RSS-Feeds</span><span class="sxs-lookup"><span data-stu-id="55cbb-102">How to: Create a Basic RSS Feed</span></span>
<span data-ttu-id="55cbb-103">Windows Communication Foundation (WCF) ermöglicht es Ihnen, einen Dienst zu erstellen, der einen Syndizierungs Feed verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="55cbb-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="55cbb-104">In diesem Thema wird erläutert, wie ein Syndication-Dienst, der einen RSS Syndication-Feed verfügbar macht, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="55cbb-104">This topic discusses how to create a syndication service that exposes an RSS syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="55cbb-105">So erstellen Sie einen grundlegenden Syndication-Dienst</span><span class="sxs-lookup"><span data-stu-id="55cbb-105">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="55cbb-106">Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="55cbb-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="55cbb-107">Jeder Vorgang, der als Syndication-Feed verfügbar gemacht wird, sollte ein <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>-Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="55cbb-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> object.</span></span>  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="55cbb-108">Alle Dienstvorgänge, die das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut übernehmen, werden HTTP GET-Anforderungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="55cbb-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> attribute are mapped to HTTP GET requests.</span></span> <span data-ttu-id="55cbb-109">Wenn Sie den Vorgang einer anderen HTTP-Methode zuordnen möchten, verwenden Sie stattdessen <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="55cbb-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="55cbb-110">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts](how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="55cbb-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2. <span data-ttu-id="55cbb-111">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="55cbb-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3. <span data-ttu-id="55cbb-112">Erstellen Sie ein <xref:System.ServiceModel.Syndication.SyndicationFeed>-Objekt, und fügen Sie einen Autor, eine Kategorie und eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="55cbb-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4. <span data-ttu-id="55cbb-113">Erstellen Sie mehrere <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="55cbb-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5. <span data-ttu-id="55cbb-114">Fügen Sie dem Feed das <xref:System.ServiceModel.Syndication.SyndicationItem> hinzu</span><span class="sxs-lookup"><span data-stu-id="55cbb-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> to the feed.</span></span>  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6. <span data-ttu-id="55cbb-115">Geben Sie den Feed zurück.</span><span class="sxs-lookup"><span data-stu-id="55cbb-115">Return the feed.</span></span>  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a><span data-ttu-id="55cbb-116">So hosten Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="55cbb-116">To host a service</span></span>  
  
1. <span data-ttu-id="55cbb-117">Erstellen eines <xref:System.ServiceModel.Web.WebServiceHost>-Objekts</span><span class="sxs-lookup"><span data-stu-id="55cbb-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2. <span data-ttu-id="55cbb-118">Öffnen Sie den Diensthost, und warten Sie, bis der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="55cbb-118">Open the service host and wait until the user presses ENTER.</span></span>  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="55cbb-119">So rufen Sie GetBlog() mit HTTP GET auf</span><span class="sxs-lookup"><span data-stu-id="55cbb-119">To call GetBlog() with an HTTP GET</span></span>  
  
1. <span data-ttu-id="55cbb-120">Öffnen Sie Internet Explorer, geben Sie die folgende URL ein, und drücken Sie die EINGABETASTE: `http://localhost:8000/BlogService/GetBlog` .</span><span class="sxs-lookup"><span data-stu-id="55cbb-120">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span> <span data-ttu-id="55cbb-121">Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/BlogService` ), die relative Adresse des Endpunkts und den aufzurufenden Dienst Vorgang.</span><span class="sxs-lookup"><span data-stu-id="55cbb-121">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="55cbb-122">So rufen Sie GetBlog() aus dem Code auf</span><span class="sxs-lookup"><span data-stu-id="55cbb-122">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="55cbb-123">Erstellen Sie einen <xref:System.Xml.XmlReader> mit der Basisadresse und der Methode, die Sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="55cbb-123">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="55cbb-124">Rufen Sie die statische <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>-Methode auf, und übergeben Sie dabei den gerade erstellten <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="55cbb-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="55cbb-125">Dies ruft einen Dienstvorgang auf und füllt einen neuen <xref:System.ServiceModel.Syndication.SyndicationFeed> mit dem vom Dienstvorgang zurückgegebenen Formatierungsprogramm auf.</span><span class="sxs-lookup"><span data-stu-id="55cbb-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="55cbb-126">Greifen Sie auf das Feedobjekt zu.</span><span class="sxs-lookup"><span data-stu-id="55cbb-126">Access the feed object.</span></span>  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="55cbb-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55cbb-127">Example</span></span>  
 <span data-ttu-id="55cbb-128">Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="55cbb-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55cbb-129">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="55cbb-129">Compiling the Code</span></span>  
 <span data-ttu-id="55cbb-130">Verweisen Sie beim Kompilieren des obigen Codes auf System.ServiceModel.dll und System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="55cbb-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cbb-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55cbb-131">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
