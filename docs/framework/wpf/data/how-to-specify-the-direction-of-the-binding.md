---
title: "Gewusst wie: Angeben der Bindungsrichtung | Microsoft Docs"
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
  - "Bindungsrichtung"
  - "Datenbindung, Richtung der Bindung"
  - "Richtung der Bindung"
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gewusst wie: Angeben der Bindungsrichtung
In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft [Bindungsziel](GTMT) \(Ziel\), [Bindungsquelle](GTMT) \(Quelle\) oder sowohl Ziel\- als auch Quelleigenschaft aktualisiert.  
  
## Beispiel  
 Mit der <xref:System.Windows.Data.Binding.Mode%2A>\-Eigenschaft geben Sie die Bindungsrichtung an.  In der folgenden Enumerationsliste werden die verfügbaren Optionen für Bindungsaktualisierungen angezeigt:  
  
-   <xref:System.Windows.Data.BindingMode> aktualisiert die Zieleigenschaft bzw. die Quelleigenschaft dann, wenn sich die Ziel\- oder die Quelleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode> aktualisiert die Zieleigenschaft nur dann, wenn sich die Quelleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode> aktualisiert die Zieleigenschaft nur dann, wenn die Anwendung gestartet wird oder wenn sich der <xref:System.Windows.FrameworkElement.DataContext%2A> ändert.  
  
-   <xref:System.Windows.Data.BindingMode> aktualisiert die Quelleigenschaft, wenn sich die Zieleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode> bewirkt, dass der <xref:System.Windows.Data.Binding.Mode%2A>\-Standardwert der Zieleigenschaft verwendet wird.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>\-Enumeration.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>\-Eigenschaft veranschaulicht.  
  
 [!code-xml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Um Quelländerungen zu erkennen \(das gilt für die <xref:System.Windows.Data.BindingMode>\-Bindung und die <xref:System.Windows.Data.BindingMode>\-Bindung\), muss die Quelle einen geeigneten Mechanismus für Benachrichtigungen bei Eigenschaftenänderungen implementieren, z. B. <xref:System.ComponentModel.INotifyPropertyChanged>.  Unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) finden Sie ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged>\-Implementierung.  
  
 Für eine <xref:System.Windows.Data.BindingMode>\-Bindung oder eine <xref:System.Windows.Data.BindingMode>Bindung können Sie das Zeitverhalten der Quellaktualisierungen durch Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Eigenschaft steuern.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## Siehe auch  
 <xref:System.Windows.Data.Binding>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)