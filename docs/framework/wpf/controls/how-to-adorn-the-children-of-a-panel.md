---
title: "Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs | Microsoft Docs"
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
  - "Adorner, Bindung an untergeordnete Elemente von Bereichen"
  - "Panel-Steuerelement, Bindung von Adornern an untergeordnete Elemente"
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs
In diesem Beispiel wird gezeigt, wie ein Adorner programmgesteuert an die untergeordneten Elemente von einem angegebenen <xref:System.Windows.Controls.Panel> gebunden wird.  
  
## Beispiel  
 Um einen Adorner an die untergeordneten Elemente eines <xref:System.Windows.Controls.Panel> zu binden, führen Sie diese Schritte aus:  
  
1.  Deklarieren Sie ein neues <xref:System.Windows.Documents.AdornerLayer>\-Objekt und rufen Sie die `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>\-Methode auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente verziert werden sollen.  
  
2.  Durchlaufen Sie die untergeordneten Elemente des übergeordneten Elements, und rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A>\-Methode auf, um einen Adorner an jedes untergeordnete Element zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner \(siehe weiter oben\) an die untergeordneten Elemente eines <xref:System.Windows.Controls.StackPanel> mit dem Namen *myStackPanel* gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Die Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Binden eines Adorners an ein anderes Element wird derzeit nicht unterstützt.  
  
## Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)