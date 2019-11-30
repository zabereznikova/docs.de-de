---
title: 'Gewusst wie: Binden von Daten an Windows Presentation Foundation-Elemente (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: b623dc10bfe1b723c62b2861b4142a138904e64a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569344"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Gewusst wie: Binden von Daten an Windows Presentation Foundation-Elemente (WCF Data Services)
Mit WCF Data Services können Sie Windows Presentation Foundation (WPF)-Elemente wie z. b. eine <xref:System.Windows.Controls.ListBox> oder <xref:System.Windows.Controls.ComboBox> an eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601>binden, die die von den Steuerelementen ausgenommenen Ereignisse behandelt, damit der <xref:System.Data.Services.Client.DataServiceContext> mit Änderungen an den Daten in den Steuerelementen synchronisiert bleibt. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ist aus der CodeBehind-Seite für eine Extensible Application Markup Language (XAML)-Seite, die das Fenster `SalesOrders` in WPF definiert. Wenn das Fenster geladen wird, wird ein <xref:System.Data.Services.Client.DataServiceCollection%601> basierend auf dem Ergebnis einer Abfrage erstellt, die Kunden nach Land/Region filtert zurückgibt. Alle Seiten dieses ausgelagerten Ergebnisses werden zusammen mit den verknüpften Bestellungen geladen und an die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des <xref:System.Windows.Controls.StackPanel> gebunden, der das Stammlayoutsteuerelement für das WPF-Fenster ist. Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert das Fenster `SalesOrders` in WPF für das vorherige Beispiel.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ist aus der CodeBehind-Seite für eine Extensible Application Markup Language (XAML)-Seite, die das Fenster `SalesOrders` in WPF definiert. Wenn das Fenster geladen wird, wird ein <xref:System.Data.Services.Client.DataServiceCollection%601> basierend auf dem Ergebnis einer Abfrage erstellt, die Kunden mit verknüpften Objekten nach Land/Region zurückgibt. Dieses Ergebnis wird an die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des <xref:System.Windows.Controls.StackPanel> gebunden, der das Stammlayoutsteuerelement für das WPF-Fenster ist.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert das Fenster `SalesOrders` in WPF für das vorherige Beispiel.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
