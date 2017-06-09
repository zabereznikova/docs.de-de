---
title: "Gewusst wie: Implementieren eines benutzerdefinierten Layoutmoduls | Microsoft Docs"
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
  - "FlowLayoutPanel-Steuerelement [Windows Forms], Layoutmodul"
  - "Layoutmodule, Benutzerdefiniert"
  - "Layoutmodule, Implementieren"
  - "LayoutEngine-Klasse"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Layoutmodul"
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Implementieren eines benutzerdefinierten Layoutmoduls
Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefiniertes Layoutmodul erstellt wird, das ein einfaches Flusslayout ausführt.  Es implementiert ein Bereichssteuerelement mit dem Namen `DemoFlowPanel`, das die <xref:System.Windows.Forms.Control.LayoutEngine%2A>\-Eigenschaft überschreibt, um eine Instanz der `DemoFlowLayout`\-Klasse bereitzustellen.  
  
## Beispiel  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.Layout.LayoutEngine>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=fullName>