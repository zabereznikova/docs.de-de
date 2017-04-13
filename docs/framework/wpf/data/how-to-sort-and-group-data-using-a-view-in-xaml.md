---
title: "Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML | Microsoft Docs"
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
  - "Datenbindung, Gruppieren von Daten in Ansichten in XAML"
  - "Datenbindung, Sortieren von Daten in Ansichten in XAML"
  - "Gruppieren von Daten in Ansichten in XAML"
  - "Sortieren von Daten in Ansichten in XAML"
  - "Ansichten, Gruppieren von Daten"
  - "Ansichten, Sortieren von Daten"
  - "XAML, Gruppieren von Daten in Ansichten"
  - "XAML, Sortieren von Daten in Ansichten"
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML
In diesem Beispiel wird gezeigt, wie eine Ansicht einer Datenauflistung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] erstellt wird.  Ansichten unterstützen das Gruppieren, Sortieren, Filtern und das Konzept eines aktuellen Elements.  
  
## Beispiel  
 Im folgenden Beispiel wird die statische Ressource *places* als Auflistung von *Place*\-Objekten definiert, in der jedes *Place*\-Objekt aus dem Namen einer Stadt und dem Bundesstaat besteht.  Dem Namespace, in dem die Datenquelle *Places* definiert ist, wird das Präfix *src* zugeordnet.  Das Präfix *scm* ist `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` zugeordnet, und *dat* ist `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` zugeordnet.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Ansicht der Datenauflistung erstellt wird, die nach dem Namen der Stadt sortiert und nach dem Bundesstaat gruppiert wird.  
  
 [!code-xml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Die Ansicht kann dann wie im folgenden Beispiel eine Bindungsquelle sein:  
  
 [!code-xml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Für Bindungen an XML\-Daten, die in einer <xref:System.Windows.Data.XmlDataProvider>\-Ressource definiert wurden, stellen Sie dem XML\-Namen ein @\-Symbol voran.  
  
 [!code-xml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## Siehe auch  
 <xref:System.Windows.Data.CollectionViewSource>   
 [Abrufen der Standardansicht einer Datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)