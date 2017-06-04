---
title: "Gewusst wie: &#220;berschreiben der Panel.OnRender-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "overriding OnRender method"
  - "Panel control, overriding OnRender method"
  - "OnRender method"
  - "controls, Panel, overriding OnRender method"
helpviewer_keywords: 
  - "OnRender-Methode, Überschreiben"
  - "Überschreiben der OnRender-Methode des Panel-Steuerelements"
  - "Panel-Steuerelement, Überschreiben der OnRender-Methode"
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: &#220;berschreiben der Panel.OnRender-Methode
Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.Panel.OnRender%2A>\-Methode von <xref:System.Windows.Controls.Panel> überschrieben wird, um einem Layoutelement benutzerdefinierte grafische Effekte hinzuzufügen.  
  
## Beispiel  
 Verwenden Sie die <xref:System.Windows.Controls.Panel.OnRender%2A>\-Methode, um einem gerenderten Bereichselement grafische Effekte hinzuzufügen.  So können Sie mit dieser Methode zum Beispiel benutzerdefinierte Rahmen\- oder Hintergrundeffekte hinzufügen.  Als Argument wird ein <xref:System.Windows.Media.DrawingContext>\-Objekt übergeben, das Methoden zum Zeichnen von Formen, für Texte, Bilder oder Videos zur Verfügung stellt.  Daher eignet sich diese Methode besonders zur Anpassung eines Bereichsobjekts.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Panel>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Beispiel für einen benutzerdefinierten radial angeordneten Bereich](http://go.microsoft.com/fwlink/?LinkID=159982)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)