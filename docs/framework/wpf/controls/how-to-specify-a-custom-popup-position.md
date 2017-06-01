---
title: "Gewusst wie: Angeben einer benutzerdefinierten Popup-Position | Microsoft Docs"
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
  - "Popup-Steuerelement, Festlegen der benutzerdefinierten Position"
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Angeben einer benutzerdefinierten Popup-Position
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Position für ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement angegeben wird, wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode> festgelegt ist.  
  
## Beispiel  
 Wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode> festgelegt ist, wird durch <xref:System.Windows.Controls.Primitives.Popup> eine definierte Instanz des <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>\-Delegats aufgerufen.  Dieses Delegat gibt einen ein Satz möglicher Punkte relativ zur oberen linken Ecke des Zielbereichs und zur oberen linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements zurück.  Die <xref:System.Windows.Controls.Primitives.Popup>\-Platzierung wird am Punkt mit der besten Sichtbarkeit ausgeführt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie die Position eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode> definiert wird.  Darüber hinaus wird das Erstellen und Zuweisen eines <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>\-Delegats zum Positionieren des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements veranschaulicht.  Der Rückrufdelegat gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>\-Objekte zurück.  Wenn das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement an der ersten Position durch den Bildschirmrand verdeckt ist, wird das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement an der zweiten Position platziert.  
  
 [!code-xml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zur Platzierung von Popups](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## Siehe auch  
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)