---
title: 'Gewusst wie: Erstellen einer Bindung an einen Webdienst'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="fc0b5-102">Gewusst wie: Erstellen einer Bindung an einen Webdienst</span><span class="sxs-lookup"><span data-stu-id="fc0b5-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="fc0b5-103">In diesem Beispiel wird gezeigt, wie zum Binden an Objekte, die durch Aufrufe des Webdiensts-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc0b5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc0b5-104">Example</span></span>  
 <span data-ttu-id="fc0b5-105">Dieses Beispiel verwendet die [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) beim Abrufen der Liste der Sprachen, die von einem angegebenen Dokument unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="fc0b5-106">Bevor Sie einen Webdienst aufrufen, müssen Sie einen Verweis darauf erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="fc0b5-107">So erstellen einen Webverweis auf den MTPS mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fc0b5-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="fc0b5-108">Öffnen Sie Ihr [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Projekt.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc0b5-109">Aus der **Projekt** Menü klicken Sie auf **Webverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="fc0b5-110">Legen Sie im Dialogfeld die **URL** auf [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="fc0b5-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="fc0b5-111">Drücken Sie **Go** und dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="fc0b5-112">Anschließend rufen Sie die Webdienstmethode und legen Sie die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuerelements oder des Fensters auf das zurückgegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="fc0b5-113">Die **GetContent** Methode des Diensts MTPS nimmt einen Verweis auf die **GetContentRequest** Objekt.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="fc0b5-114">Aus diesem Grund richtet im folgenden Beispiel wird zunächst eine Request-Objekt:</span><span class="sxs-lookup"><span data-stu-id="fc0b5-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="fc0b5-115">Nach der <xref:System.Windows.FrameworkElement.DataContext%2A> -Element festgelegt wurde, können Sie Bindungen mit den Eigenschaften des Objekts erstellen, die die <xref:System.Windows.FrameworkElement.DataContext%2A> vorsieht.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="fc0b5-116">In diesem Beispiel wird die <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt ist, um die **GetContentResponse** zurückgegebenes Objekt die **GetContent** Methode.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="fc0b5-117">Im folgenden Beispiel die <xref:System.Windows.Controls.ItemsControl> bindet an und zeigt die **Gebietsschema** Werte **AvailableVersionsAndLocales** von **GetContentResponse**.</span><span class="sxs-lookup"><span data-stu-id="fc0b5-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="fc0b5-118">Informationen zur Struktur von **GetContentResponse**, finden Sie unter [Content Service Dokumentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="fc0b5-118">For information about the structure of **getContentResponse**, see [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc0b5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc0b5-119">See Also</span></span>  
 [<span data-ttu-id="fc0b5-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="fc0b5-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fc0b5-121">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="fc0b5-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="fc0b5-122">Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="fc0b5-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
