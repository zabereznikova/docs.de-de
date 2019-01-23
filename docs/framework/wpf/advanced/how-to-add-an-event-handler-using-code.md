---
title: 'Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 4e8344ebcb0406a7da29787c5a4377760f55597e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499131"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code
Dieses Beispiel zeigt, wie ein Element mithilfe von Code einen Ereignishandler hinzugefügt wird.  
  
 Wenn Sie einen Ereignishandler hinzufügen möchten eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Element, und die Markupseite, die das Element enthält, bereits geladen wurde, müssen Sie den Handler, die mithilfe von Code. Sie können auch bei der Erstellung die Elementstruktur für eine Anwendung vollständig mithilfe von Code, und deklarieren keine Elemente mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie bestimmte Methoden zum Hinzufügen von Ereignishandlern an die Struktur der konstruierte Element aufrufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Controls.Button> zu einer vorhandenen Seite, die anfänglich in definiert ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Eine Code-Behind-Datei implementiert eine Ereignishandlermethode, und fügt diese Methode als einen neuen Ereignishandler für die <xref:System.Windows.Controls.Button>.  
  
 Die C# Beispiel verwendet die `+=` Operator, um ein Ereignis einen Handler zuzuweisen. Dies ist der gleiche Operator, der verwendet wird, weisen Sie einen Handler im der [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Modell für die Ereignisbehandlung. Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignishandlern. Es muss stattdessen eine der beiden Methoden:  
  
-   Verwenden der <xref:System.Windows.UIElement.AddHandler%2A> -Methode zusammen mit einer `AddressOf` -Operator, um auf die Implementierung des Handlers zu verweisen.  
  
-   Verwenden der `Handles` -Schlüsselwort als Teil der Definition des Ereignis-Handler. Diese Technik ist hier nicht gezeigt; finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Hinzufügen eines ereignishandlers, der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher. Fügen Sie in der Object-Element, in dem Sie den Ereignishandler hinzufügen möchten ein Attribut, das mit dem Namen des Ereignisses übereinstimmt, die Sie behandeln möchten. Geben Sie den Wert dieses Attributs als Namen für die Ereignishandlermethode, die Sie in der CodeBehind-Datei definiert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite. Weitere Informationen finden Sie unter [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) oder [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
