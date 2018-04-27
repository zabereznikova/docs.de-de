---
title: 'Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7627589ff7e422c4ad3cd7a37fdc14c8a9c9f4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-an-event-handler-using-code"></a>Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code
Dieses Beispiel zeigt, wie einen Ereignishandler mithilfe von Code ein Element hinzugefügt wird.  
  
 Wenn Sie einen Ereignishandler hinzufügen möchten eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Element, und die Markupseite, die das Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen. Auch wenn Sie die Elementstruktur für eine Anwendung vollständig mithilfe von Code und keine Elemente mit deklarieren erstellen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie bestimmte Methoden zum Hinzufügen von Ereignishandlern zu die konstruierten Elementstruktur aufrufen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird ein neues <xref:System.Windows.Controls.Button> auf eine Seite, die anfänglich in definiert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Eine Code-Behind-Datei implementiert eine Ereignishandlermethode und fügt dann diese Methode als neuen Ereignishandler auf der <xref:System.Windows.Controls.Button>.  
  
 Das C#-Beispiel verwendet die `+=` Operator, um einen Handler, ein Ereignis zugewiesen. Dies ist der gleichen Operator, der verwendet wird, weisen Sie einen Handler im die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Modell für die Ereignisbehandlung. Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignishandlern. Es muss stattdessen eine der beiden folgenden Verfahren:  
  
-   Verwenden der <xref:System.Windows.UIElement.AddHandler%2A> -Methode, zusammen mit einem `AddressOf` -Operator, um auf die Ereignishandlerimplementierung verweisen.  
  
-   Verwenden der `Handles` -Schlüsselwort als Teil der Definition des Ereignis-Handler. Diese Technik ist hier nicht gezeigt; finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Ein Ereignishandler hinzugefügt, der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher. Fügen Sie in den Object-Element, in dem der Ereignishandler hinzugefügt werden sollen ein Attribut, das den Namen des Ereignisses übereinstimmt, die Sie behandeln möchten. Geben Sie den Wert dieses Attributs als Namen für die Ereignishandlermethode, die Sie in der CodeBehind-Datei definiert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite. Weitere Informationen finden Sie unter [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) oder [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
