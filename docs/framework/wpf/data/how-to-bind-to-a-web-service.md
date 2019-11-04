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
ms.openlocfilehash: 76fa13d4a12362d04c832fd59ee69db5a6811029
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454460"
---
# <a name="how-to-bind-to-a-web-service"></a>Gewusst wie: Erstellen einer Bindung an einen Webdienst
Dieses Beispiel zeigt, wie Sie eine Bindung an Objekte herstellen, die von Webdienst Methoden aufrufen zurückgegeben werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der [Inhalts Dienst MSDN/TechNet Publishing System (MTPS)](https://go.microsoft.com/fwlink/?LinkId=95677) verwendet, um die Liste der Sprachen abzurufen, die von einem bestimmten Dokument unterstützt werden.  
  
 Bevor Sie einen Webdienst aufzurufen, müssen Sie einen Verweis darauf erstellen. Um einen Webverweis auf den MTPS-Dienst mithilfe von Visual Studio zu erstellen, führen Sie die folgenden Schritte aus:  
  
1. Öffnen Sie Ihr Projekt in Visual Studio.  
  
2. Klicken Sie im Menü **Projekt** auf **Webverweis hinzufügen**.  
  
3. Legen Sie im Dialogfeld die **URL** auf [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)fest.  
  
4. Drücken Sie die Taste **go** und dann **Verweis hinzufügen**.  
  
 Als nächstes wird die Webdienst Methode aufgerufen und die <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuer Elements oder Fensters auf das zurückgegebene Objekt festgelegt. Die `GetContent`-Methode des MTPS-Dienstanbieter nimmt einen Verweis auf das `getContentRequest`-Objekt an. Im folgenden Beispiel wird daher zuerst ein Anforderungs Objekt eingerichtet:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Nachdem die <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt wurde, können Sie Bindungen zu den Eigenschaften des Objekts erstellen, auf das der <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt wurde. In diesem Beispiel wird der <xref:System.Windows.FrameworkElement.DataContext%2A> auf das `getContentResponse` Objekt festgelegt, das von der `GetContent`-Methode zurückgegeben wird. Im folgenden Beispiel bindet der <xref:System.Windows.Controls.ItemsControl> an und zeigt die `locale` Werte `availableVersionsAndLocales` `getContentResponse`an.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Weitere Informationen zur Struktur von `getContentResponse`finden Sie in der [Dokumentation zum Inhalts Dienst](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Bereitstellen von Daten für die Bindung in XAML](how-to-make-data-available-for-binding-in-xaml.md)
