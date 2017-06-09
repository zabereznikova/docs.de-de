---
title: "Gewusst wie: Verwenden von Anwendungsressourcen | Microsoft Docs"
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
  - "Anwendungsressourcen"
  - "Ressourcen, Anwendungsressourcen"
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verwenden von Anwendungsressourcen
In diesem Beispiel wird veranschaulicht, wie Sie Anwendungsressourcen verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Anwendungsdefinitionsdatei veranschaulicht.  Die Anwendungsdefinitionsdatei definiert einen Ressourcenabschnitt \(einen Wert für die <xref:System.Windows.Application.Resources%2A>\-Eigenschaft\).  Auf Anwendungsebene definierte Ressourcen können von allen anderen zur Anwendung gehörenden Seiten aufgerufen werden.  In diesem Fall ist die Ressource ein deklarierter Stil.  Da ein vollständiger Stil, der eine Steuerelementvorlage enthält, sehr lang sein kann, wird in diesem Beispiel auf die Steuerelementvorlage verzichtet, die im <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>\-Eigenschaftensetter des Stils definiert ist.  
  
 [!code-xml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 Im folgenden Beispiel wird eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite veranschaulicht, die auf die im vorherigen Beispiel definierte Ressource auf Anwendungsebene verweist.  Auf die Ressource wird mithilfe einer [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) verwiesen, die einen eindeutigen Ressourcenschlüssel für die angeforderte Ressource angibt.  Auf der aktuellen Seite wird keine Ressource mit dem Schlüssel "GelButton" gefunden. Daraufhin wird der Ressourcensuchbereich für die angeforderte Ressource über die aktuelle Seite hinaus auf die definierten Ressourcen der Anwendungsebene ausgedehnt.  
  
 [!code-xml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## Siehe auch  
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)