---
title: "Gewusst wie: Einrichten von Benachrichtigungen &#252;ber Bindungsaktualisierungen | Microsoft Docs"
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
  - "Bindung, Aktualisierungen, Benachrichtigungen von"
  - "Datenbindung, Einrichten von Benachrichtigungen über Bindungsaktualisierungen"
  - "Benachrichtigungen, Bindungsaktualisierungen"
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Einrichten von Benachrichtigungen &#252;ber Bindungsaktualisierungen
In diesem Beispiel wird erläutert, wie Sie Benachrichtigungen einrichten können, die Sie darüber informieren, wenn die Eigenschaft [Bindungsziel](GTMT) \(Ziel\) oder [Bindungsquelle](GTMT) \(Quelle\) einer Bindung aktualisiert wurde.  
  
## Beispiel  
 Bei jeder Aktualisierung der Bindungsquelle oder des Bindungsziels löst [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein Datenaktualisierungsereignis aus.  Intern veranlasst dieses Ereignis die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], eine Aktualisierung durchzuführen, weil sich die gebundenen Daten geändert haben.  Beachten Sie, dass Sie Ihre Datenklasse mithilfe der <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementieren müssen, damit diese Ereignisse sowie unidirektionale bzw. bidirektionale Bindungen ordnungsgemäß funktionieren.  Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Legen Sie die Eigenschaft <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> oder <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> \(oder beide\) in der Bindung auf `true` fest.  Der Handler, den Sie zur Überwachung dieses Ereignisses bereitstellen, muss direkt an das Element angefügt werden, über dessen Änderungen Sie informiert werden möchten. Oder er muss an den Gesamtdatenkontext angefügt werden, wenn Sie über Änderungen am Kontext informiert werden möchten.  
  
 Im folgenden Beispiel wird erläutert, wie Sie Benachrichtigungen für die Aktualisierung einer Zieleigenschaft einrichten.  
  
 [!code-xml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Anschließend können Sie zur Behandlung des Ereignisses einen Handler auf Grundlage des EventHandler\<T\>\-Delegats einrichten, in diesem Beispiel *OnTargetUpdated*:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Parameter des Ereignisses können zur Ermittlung von Details über die geänderte Eigenschaft \(z. B. den Typ oder das jeweilige Element, wenn derselbe Handler an mehrere Elemente angefügt ist\) verwendet werden. Diese Details können hilfreich sein, wenn es für ein einzelnes Element mehrere gebundene Eigenschaften gibt.  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)