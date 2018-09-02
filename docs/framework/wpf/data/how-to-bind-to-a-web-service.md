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
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420301"
---
# <a name="how-to-bind-to-a-web-service"></a>Gewusst wie: Erstellen einer Bindung an einen Webdienst
Dieses Beispiel zeigt, wie zum Binden an Objekte, die durch Aufrufe des Webdiensts-Methode zurückgegeben wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die [MSDN/TechNet Publishing System (MTPS) Inhaltsdiensts](https://go.microsoft.com/fwlink/?LinkId=95677) zum Abrufen der Liste der Sprachen, die von einem angegebenen Dokument unterstützt.  
  
 Bevor Sie einen Webdienst aufrufen, müssen Sie einen Verweis darauf erstellen. Erstellen Sie einen Webverweis auf den Dienst mit MTPS [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], befolgen Sie die folgenden Schritte aus:  
  
1.  Öffnen Sie Ihr [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Projekt.  
  
2.  Von der **Projekt** Menü klicken Sie auf **Webverweis hinzufügen**.  
  
3.  Legen Sie im Dialogfeld die **URL** zu [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Drücken Sie **wechseln** und dann **Verweis hinzufügen**.  
  
 Anschließend rufen Sie die Webdienstmethode und legen Sie die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuerelements oder des Fenster auf das zurückgegebene Objekt. Die **GetContent** -Methode des Diensts MTPS akzeptiert einen Verweis auf die **GetContentRequest** Objekt. Aus diesem Grund legt im folgenden Beispiel wird zuerst ein Anforderungsobjekt fest:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Nach der <xref:System.Windows.FrameworkElement.DataContext%2A> -Element festgelegt wurde, können Sie Bindungen für die Eigenschaften des Objekts erstellen, die die <xref:System.Windows.FrameworkElement.DataContext%2A> auf festgelegt wurde. In diesem Beispiel die <xref:System.Windows.FrameworkElement.DataContext%2A> nastaven NA hodnotu der **getContent** zurückgegebenes Objekt der **GetContent** Methode. Im folgenden Beispiel die <xref:System.Windows.Controls.ItemsControl> bindet an und zeigt die **Gebietsschema** Werte **AvailableVersionsAndLocales** von **getContent**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Informationen zur Struktur von **getContent**, finden Sie unter [Dokumentation zu Content Service](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
