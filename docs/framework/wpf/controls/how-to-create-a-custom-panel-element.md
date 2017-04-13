---
title: "Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements | Microsoft Docs"
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
  - "Benutzerdefinierte Panel-Elemente"
  - "Panel-Steuerelement"
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements
## Beispiel  
 In diesem Beispiel wird dargestellt, wie das Standardlayoutverhalten des <xref:System.Windows.Controls.Panel>\-Elements überschrieben werden kann und benutzerdefinierte Layoutelemente erstellt werden, die von <xref:System.Windows.Controls.Panel> abgeleitet sind.  
  
 In diesem Beispiel wird ein einfaches benutzerdefiniertes <xref:System.Windows.Controls.Panel>\-Element \(`PlotPanel`\) definiert, das untergeordnete Elemente zwei fest programmierten x\- und y\-Koordinaten entsprechend positioniert.  Außerdem werden in diesem Beispiel `x` und `y` auf `50` festgelegt, d. h. alle untergeordneten Elemente werden auf der x\-Achse und auf der Y\-Achse an dieser Position platziert.  
  
 Zur Implementierung von benutzerdefiniertem <xref:System.Windows.Controls.Panel>\-Verhalten werden in diesem Beispiel die Methoden <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> angewendet.  Jede Methode gibt die <xref:System.Windows.Size>\-Daten zurück, die zur Positionierung und zum Rendern von untergeordnete Elemente notwendig sind.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Panel>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Erstellen eines Beispiels für einen Bereich mit benutzerdefiniertem Inhaltsumbruch](http://go.microsoft.com/fwlink/?LinkID=159979)