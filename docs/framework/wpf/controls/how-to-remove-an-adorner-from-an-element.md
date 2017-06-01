---
title: "Gewusst wie: Entfernen eines Adorners aus einem Element | Microsoft Docs"
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
  - "Adorner, Entfernen"
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Entfernen eines Adorners aus einem Element
Dieses Beispiel zeigt, wie Sie einen bestimmten Adorner programmgesteuert aus einem angegebenen <xref:System.Windows.UIElement> entfernen.  
  
## Beispiel  
 In diesem ausführlichen Codebeispiel wird der erste Adorner im Array mit Adornern entfernt, das von <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> zurückgegeben wird.  In diesem Beispiel werden die Adorner für ein <xref:System.Windows.UIElement> mit dem Namen *myTextBox* abgerufen.  Wenn das Element, das im Aufruf von <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> angegeben ist, keine Adorner aufweist, wird `null` zurückgegeben.  Dieser Code führt eine explizite Prüfung auf ein NULL\-Array durch und eignet sich am besten für Anwendungen, in denen ein NULL\-Array relativ häufig vorkommt.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## Beispiel  
 Dieses gekürzte Codebeispiel entspricht in Bezug auf seine Funktion dem oben gezeigten ausführlichen Beispiel.  Dieser Code führt keine explizite Prüfung auf ein NULL\-Array durch, so dass ggf. eine <xref:System.NullReferenceException>\-Ausnahme ausgelöst wird.  Dieser Code eignet sich am besten für Anwendungen, in denen ein NULL\-Array nicht häufig verwendet wird.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)