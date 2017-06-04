---
title: "Gewusst wie: Verwenden einer Steuerelementwiedergabeklasse | Microsoft Docs"
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
  - "Professionelle Darstellung, Wiedergabe von Windows Forms-Steuerelementen"
  - "Visuelle Stile, Wiedergabe von Windows Forms-Steuerelementen"
  - "Visuelle Designs, Anwenden auf Windows Forms-Steuerelemente"
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verwenden einer Steuerelementwiedergabeklasse
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.ComboBoxRenderer>\-Klasse verwendet wird, um den Dropdownpfeil eines Kombinationsfeldsteuerelements zu rendern.  Das Beispiel umfasst die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode eines einfachen benutzerdefinierten Steuerelements.  Die <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=fullName>\-Eigenschaft wird verwendet, um zu bestimmen, ob visuelle Stile im Clientbereich von Anwendungsfenstern aktiviert sind.  Wenn visuelle Stile aktiviert sind, gibt die <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=fullName>\-Methode den Dropdownpfeil mit visuellen Stilen wieder. Andernfalls gibt die <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=fullName>\-Methode den Dropdownpfeil im klassischen Windows\-Stil wieder.  
  
## Beispiel  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein benutzerdefiniertes Steuerelement, das von der <xref:System.Windows.Forms.Control>\-Klasse abgeleitet ist.  
  
-   Ein <xref:System.Windows.Forms.Form>, das das benutzerdefinierte Steuerelement hostet.  
  
-   Verweise auf die Namespaces <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> und <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## Siehe auch  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)