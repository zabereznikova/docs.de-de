---
title: "Gewusst wie: Treffertest in Viewport3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Grafische 3D-Elemente, Treffertests für"
  - "Treffertests, Für grafische 3D-Elemente"
  - "Viewport3D"
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Treffertest in Viewport3D
In diesem Beispiel wird veranschaulicht, wie Sie einen Treffertest für visuelle 3D\-Elemente in <xref:System.Windows.Controls.Viewport3D> ausführen.  
  
 Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D\- und 3D\-Informationen zurückgibt, ist es möglich, die Ergebnisse des Tests nur nach den 3D\-Ergebnissen zu durchsuchen.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 Das <xref:System.Windows.Media.HitTestResultBehavior>\-Element bestimmt im folgenden Code, wie die Ergebnisse des Treffertests verarbeitet werden.  `UpdateResultInfo` und `UpdateMaterial` sind lokal definierte Methoden.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## Siehe auch  
 [Beispiel für eine 3D\-Trefferüberprüfung](http://go.microsoft.com/fwlink/?LinkID=159959)