---
title: "Gewusst wie: Binden eines Adorners an ein Element | Microsoft Docs"
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
  - "Adorner, Binden an angegebene UIElements"
  - "UIElements, Bindung von Adornern an"
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Binden eines Adorners an ein Element
In diesem Beispiel wird gezeigt, wie ein Adorner programmgesteuert an ein angegebenes <xref:System.Windows.UIElement> gebunden wird.  
  
## Beispiel  
 Um einen Adorner an ein bestimmtes <xref:System.Windows.UIElement> zu binden, führen Sie die folgenden Schritte aus:  
  
1.  Rufen Sie die `static`\-Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> auf, um ein <xref:System.Windows.Documents.AdornerLayer>\-Objekt für das zu verzierende <xref:System.Windows.UIElement>\-Element abzurufen.  <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> durchläuft, beginnend am angegebenen **UIElement** , die visuelle Struktur und gibt die erste gefundene Adornerebene zurück.  \(Wenn keine Adornerebenen gefunden werden, gibt die Methode NULL zurück.\)  
  
2.  Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A>\-Methode auf, um den Adorner an das Ziel\-**UIElement** zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner \(siehe weiter oben\) an ein <xref:System.Windows.Controls.TextBox> mit dem Namen *myTextBox* gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Die Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Binden eines Adorners an ein anderes Element wird derzeit nicht unterstützt.  
  
## Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)