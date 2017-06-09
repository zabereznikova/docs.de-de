---
title: "Gewusst wie: Erstellen einer Bindung an einen Webdienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Binden von Daten, Webdienst"
  - "Datenbindung, Webdienst"
  - "Webdienstbindung"
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer Bindung an einen Webdienst
Dieses Beispiel zeigt, wie eine Bindung an Objekte erstellt wird, die von Aufrufen der Webdienstmethode zurückgegeben wurden.  
  
## Beispiel  
 Dieses Beispiel verwendet den [MSDN\/TechNet Publishing System \(MTPS\) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677), um die vom angegebenen Dokument unterstützten Sprachen abzurufen.  
  
 Bevor Sie einen Webdienst aufrufen, müssen Sie einen Verweis darauf erstellen.  Um in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] einen Webverweis auf den MTPS\-Dienst zu erstellen, führen Sie folgende Schritte aus:  
  
1.  Öffnen Sie das Projekt in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  Klicken Sie im Menü **Projekt** auf **Webverweis hinzufügen**.  
  
3.  Geben Sie im Dialogfeld die **URL** [http:\/\/services.msdn.microsoft.com\/contentservices\/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl) an.  
  
4.  Klicken Sie auf **Gehe zu** und dann auf **Verweis hinzufügen**.  
  
 Rufen Sie anschließend die Webdienstmethode auf, und legen Sie den <xref:System.Windows.FrameworkElement.DataContext%2A> des entsprechenden Steuerelements oder Fensters auf das zurückgegebene Objekt fest.  Die **GetContent**\-Methode des MTPS\-Diensts übernimmt einen Verweis auf das **getContentRequest**\-Objekt.  Aus diesem Grund wird im folgenden Beispiel zuerst ein Anforderungsobjekt eingerichtet:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Nachdem der <xref:System.Windows.FrameworkElement.DataContext%2A> eingerichtet wurde, können Sie die Bindungen zu den Eigenschaften des Objekts erstellen, auf das der <xref:System.Windows.FrameworkElement.DataContext%2A> festgelegt wurde.  In diesem Beispiel wird der <xref:System.Windows.FrameworkElement.DataContext%2A> auf das von der **GetContent**\-Methode zurückgegebene **getContentResponse**\-Objekt festgelegt.  Im folgenden Beispiel stellt das <xref:System.Windows.Controls.ItemsControl> eine Bindung zu den **locale**\-Werten aus **availableVersionsAndLocales** von **getContentResponse** her und zeigt sie an.  
  
 [!code-xml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Informationen über die Struktur von **getContentResponse** finden Sie unter [Content Service Documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)