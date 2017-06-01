---
title: "Gewusst wie: Entfernen aller Adorner aus einem Element | Microsoft Docs"
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
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Entfernen aller Adorner aus einem Element
In diesem Beispiel wird gezeigt, wie alle Adorner programmgesteuert aus einem angegebenen <xref:System.Windows.UIElement> entfernt werden.  
  
## Beispiel  
 In diesem ausführlichen Codebeispiel werden alle Adorner im Array mit Adornern entfernt, das von <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> zurückgegeben wird.  In diesem Beispiel werden die Adorner für ein <xref:System.Windows.UIElement> mit dem Namen *myTextBox* abgerufen.  Wenn das Element, das im Aufruf von <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> angegeben ist, keine Adorner aufweist, wird `null` zurückgegeben.  Dieser Code führt eine explizite Prüfung auf ein NULL\-Array durch und eignet sich am besten für Anwendungen, in denen ein NULL\-Array relativ häufig vorkommt.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## Beispiel  
 Dieses gekürzte Codebeispiel entspricht in Bezug auf seine Funktion dem oben gezeigten ausführlichen Beispiel.  Dieser Code führt keine explizite Prüfung auf ein NULL\-Array durch, so dass ggf. eine <xref:System.NullReferenceException>\-Ausnahme ausgelöst wird.  Dieser Code eignet sich am besten für Anwendungen, in denen ein NULL\-Array nicht häufig verwendet wird.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)