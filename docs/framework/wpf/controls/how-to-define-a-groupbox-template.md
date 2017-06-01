---
title: "Gewusst wie: Definieren einer GroupBox-Vorlage | Microsoft Docs"
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
  - "Steuerelemente, GroupBox"
  - "GroupBox-Steuerelement, Erstellen von Vorlagen"
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Definieren einer GroupBox-Vorlage
In diesem Beispiel wird dargestellt, wie Sie eine Vorlage für ein <xref:System.Windows.Controls.GroupBox>\-Steuerelement erstellen.  
  
## Beispiel  
 In folgendem Beispiel wird eine <xref:System.Windows.Controls.GroupBox>\-Steuerelementvorlage definiert, indem ein <xref:System.Windows.Controls.Grid>\-Steuerelement für das Layout verwendet wird.  In der Vorlage wird mit <xref:System.Windows.Controls.BorderGapMaskConverter> der Rahmen des <xref:System.Windows.Controls.GroupBox>\-Steuerelements so definiert, dass der Rahmen nicht den <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>\-Inhalt verdeckt.  
  
 [!code-xml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GroupBox>   
 [GroupBox How\-to Topics](http://msdn.microsoft.com/de-de/7692e155-a4c6-428c-b7e0-64b3740daca7)