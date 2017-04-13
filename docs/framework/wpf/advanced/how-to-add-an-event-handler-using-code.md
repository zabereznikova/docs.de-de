---
title: "Gewusst wie: Hinzuf&#252;gen eines Ereignishandlers mithilfe von Code | Microsoft Docs"
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
  - "Ereignishandler, Hinzufügen"
  - "XAML, Hinzufügen von Ereignishandlern"
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen eines Ereignishandlers mithilfe von Code
In diesem Beispiel wird veranschaulicht, wie ein Ereignishandler einem Element mithilfe von Code hinzugefügt.  
  
 Wenn Sie einen Ereignishandler einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Element hinzufügen möchten und die Markupseite, die das Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen.  Sie haben aber auch die Möglichkeit, spezielle Methoden zum Hinzufügen von Ereignishandlern zu der erstellen Elementstruktur aufzurufen, wenn Sie die Elementstruktur für eine Anwendung insgesamt mithilfe von Code erstellen und Elemente nicht mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deklarieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine neue <xref:System.Windows.Controls.Button> einer vorhandenen Seite hinzugefügt, die anfänglich in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definiert wurde.  Eine Code\-Behind\-Datei implementiert eine Ereignishandlermethode und fügt dann diese Methode als neuen Ereignishandler der <xref:System.Windows.Controls.Button> hinzu.  
  
 Im [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)]\-Beispiel wird der Operator `+=` verwendet, um einen Handler einem Ereignis zuzuweisen.  Dieser Operator wird auch verwendet, um einen Handler im [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Ereignisbehandlungsmodell zuzuweisen.  [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignishandlern.  Stattdessen ist eines der beiden folgenden Verfahren erforderlich:  
  
-   Verwenden Sie die <xref:System.Windows.UIElement.AddHandler%2A>\-Methode, zusammen mit einem Operator `AddressOf`, um auf die Ereignishandlerimplementierung zu verweisen.  
  
-   Verwenden Sie das `Handles`\-Schlüsselwort als Teil der Ereignishandlerdefinition.  Dieses Verfahren wird nicht hier beschrieben. Nähere Informationen hierzu finden Sie unter [Visual Basic\- und WPF\-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Es ist viel einfacher, der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite einen Ereignishandler hinzuzufügen.  Fügen Sie innerhalb des Objektelements an der Stelle, an der Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Elements entspricht, das Sie behandeln möchten.  Geben Sie dann den Wert dieses Attributs als Namen der Handlermethode an, die Sie in der Code\-Behind\-Datei der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite definiert haben.  Weitere Informationen finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) oder unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)