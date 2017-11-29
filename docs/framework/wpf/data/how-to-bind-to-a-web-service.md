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
# <a name="how-to-bind-to-a-web-service"></a>Gewusst wie: Erstellen einer Bindung an einen Webdienst
In diesem Beispiel wird gezeigt, wie zum Binden an Objekte, die durch Aufrufe des Webdiensts-Methode zurückgegeben wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) beim Abrufen der Liste der Sprachen, die von einem angegebenen Dokument unterstützt.  
  
 Bevor Sie einen Webdienst aufrufen, müssen Sie einen Verweis darauf erstellen. So erstellen einen Webverweis auf den MTPS mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], führen Sie die folgenden Schritte aus:  
  
1.  Öffnen Sie Ihr [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Projekt.  
  
2.  Aus der **Projekt** Menü klicken Sie auf **Webverweis hinzufügen**.  
  
3.  Legen Sie im Dialogfeld die **URL** auf [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Drücken Sie **Go** und dann **Verweis hinzufügen**.  
  
 Anschließend rufen Sie die Webdienstmethode und legen Sie die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuerelements oder des Fensters auf das zurückgegebene Objekt. Die **GetContent** Methode des Diensts MTPS nimmt einen Verweis auf die **GetContentRequest** Objekt. Aus diesem Grund richtet im folgenden Beispiel wird zunächst eine Request-Objekt:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Nach der <xref:System.Windows.FrameworkElement.DataContext%2A> -Element festgelegt wurde, können Sie Bindungen mit den Eigenschaften des Objekts erstellen, die die <xref:System.Windows.FrameworkElement.DataContext%2A> vorsieht. In diesem Beispiel wird die <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt ist, um die **GetContentResponse** zurückgegebenes Objekt die **GetContent** Methode. Im folgenden Beispiel die <xref:System.Windows.Controls.ItemsControl> bindet an und zeigt die **Gebietsschema** Werte **AvailableVersionsAndLocales** von **GetContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Informationen zur Struktur von **GetContentResponse**, finden Sie unter [Content Service Dokumentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
