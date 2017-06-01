---
title: "Gewusst wie: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Asynchrone Vorgänge"
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie aus einem Datendienst abgerufene Daten an Benutzeroberflächenelemente einer WPF \(Windows Presentation Framework\)\-Anwendung binden.  Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Sie können außerdem Vorgänge für den Datendienst asynchron ausführen, wodurch die Anwendung beim Warten auf eine Antwort auf die Datendienstanforderung weiterhin reagieren kann.  Anwendungen für Silverlight sind erforderlich, um asynchron auf den Datendienst zuzugreifen.  Weitere Informationen finden Sie unter [Asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 In diesem Thema wird gezeigt, wie asynchron auf einen Datendienst zugegriffen wird und die Ergebnisse an Elemente einer WPF\-Anwendung gebunden werden.  In den Beispielen in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Der folgende XAML\-Code definiert das Fenster der WPF\-Anwendung.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## Beispiel  
 Die folgende Code\-Behind\-Seite für die XAML\-Datei führt mit dem Datendienst eine asynchrone Abfrage aus und bindet die Ergebnisse an Elemente im WPF\-Fenster.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)