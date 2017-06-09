---
title: "Gewusst wie: Binden von Daten an Windows Presentation Foundation-Elemente (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung, WCF Data Services"
  - "WCF Data Services, Datenbindung"
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Binden von Daten an Windows Presentation Foundation-Elemente (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie WPF \(Windows Presentation Foundation\)\-Elemente wie ein <xref:System.Windows.Controls.ListBox>``\-Steuerelement oder ein <xref:System.Windows.Controls.ComboBox>\-Steuerelement an eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> binden, die die von den Steuerelementen ausgelösten Ereignisse behandelt, damit der <xref:System.Data.Services.Client.DataServiceContext>\-Kontext mit an Daten in den Steuerelementen vorgenommenen Änderungen synchron bleibt.  Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Das folgende Beispiel ist aus der CodeBehind\-Seite für eine Extensible Application Markup Language \(XAML\)\-Seite, die das Fenster `SalesOrders` in WPF definiert.  Wenn das Fenster geladen wird, wird eine <xref:System.Data.Services.Client.DataServiceCollection%601> basierend auf dem Ergebnis einer Abfrage erstellt, die Kunden nach Land gefiltert zurückgibt.  Alle Seiten dieses ausgelagerten Ergebnisses werden zusammen mit den verknüpften Bestellungen geladen und an die <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft des <xref:System.Windows.Controls.StackPanel> gebunden, der das Stammlayoutsteuerelement für das WPF\-Fenster ist.  Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## Beispiel  
 Der folgende XAML\-Code definiert das Fenster `SalesOrders` in WPF für das vorherige Beispiel.  
  
 [!code-xml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## Beispiel  
 Das folgende Beispiel ist aus der CodeBehind\-Seite für eine Extensible Application Markup Language \(XAML\)\-Seite, die das Fenster `SalesOrders` in WPF definiert.  Wenn das Fenster geladen wird, wird eine <xref:System.Data.Services.Client.DataServiceCollection%601> basierend auf dem Ergebnis einer Abfrage erstellt, die Kunden mit verknüpften Objekten nach Land gefiltert zurückgibt.  Dieses Ergebnis wird an die <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft des <xref:System.Windows.Controls.StackPanel> gebunden, der das Stammlayoutsteuerelement für das WPF\-Fenster ist.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## Beispiel  
 Der folgende XAML\-Code definiert das Fenster `SalesOrders` in WPF für das vorherige Beispiel.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]