---
title: "Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen | Microsoft Docs"
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
  - "Bindungseigenschaften von zwei Steuerelementen"
  - "Steuerelemente, Bindungseigenschaften von"
  - "Datenbindung, Bindungseigenschaften von zwei Steuerelementen"
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen
In diesem Beispiel wird erläutert, wie die Eigenschaft eines instanziierten Steuerelements mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A>\-Eigenschaft an die Eigenschaft eines anderen Steuerelements gebunden wird.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Panel.Background%2A>\-Eigenschaft von <xref:System.Windows.Controls.Canvas> an die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft von <xref:System.Windows.Controls.ComboBox> gebunden wird:  
  
 [!code-xml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Wenn dieses Beispiel gerendert wird, sieht es folgendermaßen aus:  
  
 ![Ein Canvas mit grünem Hintergrund](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.png "DataBindingBindingDPsSample")  
  
 **Hinweis** Die [Bindungsziel](GTMT)\-Eigenschaft \(in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A>\-Eigenschaft\) muss eine [Abhängigkeitseigenschaft](GTMT) sein.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## Siehe auch  
 [Angeben der Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)