---
title: 'Gewusst wie: Erstellen einer Bindung an einen Webdienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 84c5aee8d2bc7d31ebcfee98930d9a0847c527d5
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44704799"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="4a6e6-102">Gewusst wie: Erstellen einer Bindung an einen Webdienst</span><span class="sxs-lookup"><span data-stu-id="4a6e6-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="4a6e6-103">Dieses Beispiel zeigt, wie zum Binden an Objekte, die durch Aufrufe des Webdiensts-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a6e6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a6e6-104">Example</span></span>  
 <span data-ttu-id="4a6e6-105">Dieses Beispiel verwendet die [MSDN/TechNet Publishing System (MTPS) Inhaltsdiensts](https://go.microsoft.com/fwlink/?LinkId=95677) zum Abrufen der Liste der Sprachen, die von einem angegebenen Dokument unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="4a6e6-106">Bevor Sie einen Webdienst aufrufen, müssen Sie einen Verweis darauf erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="4a6e6-107">Erstellen Sie einen Webverweis auf den Dienst mit MTPS [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], befolgen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4a6e6-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="4a6e6-108">Öffnen Sie Ihr [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Projekt.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a6e6-109">Von der **Projekt** Menü klicken Sie auf **Webverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="4a6e6-110">Legen Sie im Dialogfeld die **URL** zu [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="4a6e6-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="4a6e6-111">Drücken Sie **wechseln** und dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="4a6e6-112">Anschließend rufen Sie die Webdienstmethode und legen Sie die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuerelements oder des Fenster auf das zurückgegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="4a6e6-113">Die **GetContent** -Methode des Diensts MTPS akzeptiert einen Verweis auf die **GetContentRequest** Objekt.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="4a6e6-114">Aus diesem Grund legt im folgenden Beispiel wird zuerst ein Anforderungsobjekt fest:</span><span class="sxs-lookup"><span data-stu-id="4a6e6-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="4a6e6-115">Nach der <xref:System.Windows.FrameworkElement.DataContext%2A> -Element festgelegt wurde, können Sie Bindungen für die Eigenschaften des Objekts erstellen, die die <xref:System.Windows.FrameworkElement.DataContext%2A> auf festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="4a6e6-116">In diesem Beispiel die <xref:System.Windows.FrameworkElement.DataContext%2A> nastaven NA hodnotu der **getContent** zurückgegebenes Objekt der **GetContent** Methode.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="4a6e6-117">Im folgenden Beispiel die <xref:System.Windows.Controls.ItemsControl> bindet an und zeigt die **Gebietsschema** Werte **AvailableVersionsAndLocales** von **getContent**.</span><span class="sxs-lookup"><span data-stu-id="4a6e6-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="4a6e6-118">Informationen zur Struktur von **getContent**, finden Sie unter [Dokumentation zu Content Service](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="4a6e6-118">For information about the structure of **getContentResponse**, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6e6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a6e6-119">See Also</span></span>  
 [<span data-ttu-id="4a6e6-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="4a6e6-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="4a6e6-121">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="4a6e6-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="4a6e6-122">Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="4a6e6-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
