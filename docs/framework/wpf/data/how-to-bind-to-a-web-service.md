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
ms.openlocfilehash: 72638101b73e6b43fa225885b2e1f27d87b22826
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920143"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="8e03e-102">Gewusst wie: Erstellen einer Bindung an einen Webdienst</span><span class="sxs-lookup"><span data-stu-id="8e03e-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="8e03e-103">Dieses Beispiel zeigt, wie Sie eine Bindung an Objekte herstellen, die von Webdienst Methoden aufrufen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e03e-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e03e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e03e-104">Example</span></span>  
 <span data-ttu-id="8e03e-105">In diesem Beispiel wird der [Inhalts Dienst MSDN/TechNet Publishing System (MTPS)](https://go.microsoft.com/fwlink/?LinkId=95677) verwendet, um die Liste der Sprachen abzurufen, die von einem bestimmten Dokument unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8e03e-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="8e03e-106">Bevor Sie einen Webdienst aufzurufen, müssen Sie einen Verweis darauf erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e03e-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="8e03e-107">Um einen Webverweis auf den MTPS-Dienst mithilfe von Visual Studio zu erstellen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8e03e-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="8e03e-108">Öffnen Sie Ihr Projekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e03e-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="8e03e-109">Klicken Sie im Menü **Projekt** auf **Webverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8e03e-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="8e03e-110">Legen Sie im Dialogfeld die **URL** auf [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)fest.</span><span class="sxs-lookup"><span data-stu-id="8e03e-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="8e03e-111">Drücken Sie die Taste **go** und dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8e03e-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="8e03e-112">Als nächstes wird die Webdienst Methode aufgerufen und die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuer Elements oder Fensters auf das zurückgegebene Objekt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e03e-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="8e03e-113">Die **getContent** -Methode des MTPS-Dienstanbieter nimmt einen Verweis auf das **getContentRequest** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="8e03e-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="8e03e-114">Im folgenden Beispiel wird daher zuerst ein Anforderungs Objekt eingerichtet:</span><span class="sxs-lookup"><span data-stu-id="8e03e-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="8e03e-115">Nachdem die <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt wurde, können Sie Bindungen zu den Eigenschaften des Objekts erstellen, auf das der <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="8e03e-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="8e03e-116">In diesem Beispiel wird der <xref:System.Windows.FrameworkElement.DataContext%2A> auf das **getContentResponse** -Objekt festgelegt, das von der **getContent** -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8e03e-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="8e03e-117">Im folgenden Beispiel bindet der <xref:System.Windows.Controls.ItemsControl> an und zeigt die Gebiets Schema **Werte von** **availableversionsandlocale** von **getContentResponse**an.</span><span class="sxs-lookup"><span data-stu-id="8e03e-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="8e03e-118">Weitere Informationen zur Struktur von **getContentResponse**finden Sie in der [Dokumentation zum Inhalts Dienst](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="8e03e-118">For information about the structure of **getContentResponse**, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e03e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e03e-119">See also</span></span>

- [<span data-ttu-id="8e03e-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="8e03e-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="8e03e-121">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="8e03e-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="8e03e-122">Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="8e03e-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
