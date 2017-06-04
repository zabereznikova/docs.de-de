---
title: "Gewusst wie: Ausw&#228;hlen eines Elements im ListView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Listenansichten, Auswählen von Elementen"
  - "Listen, Auswählen von Elementen"
  - "ListView-Steuerelement [Windows Forms], Auswählen von Elementen"
  - "Auswahl, In Listenansichten"
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Ausw&#228;hlen eines Elements im ListView-Steuerelement in Windows&#160;Forms
In diesem Beispiel wird veranschaulicht, wie ein Element programmgesteuert in einem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms ausgewählt wird.  Wenn Sie ein Element programmgesteuert auswählen, wird der Fokus nicht automatisch auf das <xref:System.Windows.Forms.ListView>\-Steuerelement geändert.  Daher sollten Sie beim Auswählen eines Elements normalerweise auch den Fokus auf das Element festlegen.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.ListView>\-Steuerelement mit dem Namen `listView1`, das mindestens ein Element enthält.  
  
-   Verweise auf den <xref:System?displayProperty=fullName>\-Namespace und den <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=fullName>