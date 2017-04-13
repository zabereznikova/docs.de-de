---
title: "Gewusst wie: &#196;ndern der Farbe eines Elements mithilfe von Fokusereignissen | Microsoft Docs"
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
  - "Farben von Elementen, Ändern"
  - "Elemente, Ändern der Farbe von"
  - "Fokusereignisse, Ändern der Elementfarbe für"
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: &#196;ndern der Farbe eines Elements mithilfe von Fokusereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern, wenn es den Fokus erhält bzw. verliert, indem Sie die Ereignisse <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> verwenden.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei und einer Code\-Behind\-Datei.  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]\-Code erstellt die Benutzeroberfläche, die aus zwei <xref:System.Windows.Controls.Button>\-Objekten besteht, und fügt Ereignishandler für die Ereignisse <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> an die <xref:System.Windows.Controls.Button>\-Objekte an.  
  
 [!code-xml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Der folgende Code\-Behind erstellt die Ereignishandler <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus>.  Wenn <xref:System.Windows.Controls.Button> den Tastaturfokus erhält, wird der <xref:System.Windows.Controls.Control.Background%2A> von <xref:System.Windows.Controls.Button> in die Farbe Rot geändert.  Wenn <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, wird der <xref:System.Windows.Controls.Control.Background%2A> von <xref:System.Windows.Controls.Button> in die Farbe Weiß geändert.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)