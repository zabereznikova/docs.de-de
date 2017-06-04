---
title: "Gewusst wie: Rendern eines visuellen Stilelements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Professionelle Darstellung, Anwenden auf Elemente in Windows Forms-Anwendungen"
  - "Visuelle Stile, Wiedergabe von Windows Forms-Steuerelementen"
  - "Visuelle Designs, Anwenden auf Elemente in Windows Forms-Anwendungen"
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Rendern eines visuellen Stilelements
Der <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>\-Namespace macht <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>\-Objekte verfügbar, die den von visuellen Stilen unterstützten Windows\-Benutzeroberflächenelementen entsprechen.  Dieses Thema zeigt, wie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>\-Klasse zum Rendern des <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> verwendet wird, das den Schaltflächen **Abmelden** und **Beenden** im Startmenü entspricht.  
  
### So rendern Sie ein visuelles Stilelement  
  
1.  Erstellen Sie einen <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>, und legen Sie ihn auf das Element fest, das Sie zeichnen möchten.  Beachten Sie die Verwendung der <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=fullName>\-Eigenschaft und der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=fullName>\-Methode. Der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A>\-Konstruktor löst eine Ausnahme aus, wenn visuelle Stile deaktiviert sind oder ein Element nicht definiert ist.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Rufen Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A>\-Methode auf, um das Element zu rendern, das der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> derzeit darstellt.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein benutzerdefiniertes Steuerelement, das von der <xref:System.Windows.Forms.Control>\-Klasse abgeleitet ist.  
  
-   Ein <xref:System.Windows.Forms.Form>, das das benutzerdefinierte Steuerelement hostet.  
  
-   Verweise auf die Namespaces <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> und <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## Siehe auch  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)