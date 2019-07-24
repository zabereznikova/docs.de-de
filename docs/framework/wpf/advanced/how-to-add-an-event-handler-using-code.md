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
ms.openlocfilehash: 00b12d9dc25e0704eb73d8bc727ae6647493f494
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401167"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Vorgehensweise: Hinzufügen eines Ereignishandlers mithilfe von Code
In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.  
  
 Wenn Sie einem- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Element einen Ereignishandler hinzufügen möchten und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen. Wenn Sie die Elementstruktur für eine Anwendung, die vollständig Code verwendet, und keine Elemente mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]von deklarieren, können Sie alternativ bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird einer vorhandenen <xref:System.Windows.Controls.Button> Seite, die anfänglich in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist, ein neues hinzugefügt. Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler für <xref:System.Windows.Controls.Button>hinzu.  
  
 Im C# Beispiel wird der `+=` -Operator verwendet, um einem Ereignis einen Handler zuzuweisen. Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen. Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern. Stattdessen ist eine von zwei Methoden erforderlich:  
  
- Verwenden Sie <xref:System.Windows.UIElement.AddHandler%2A> die-Methode und einen `AddressOf` -Operator, um auf die Ereignishandlerimplementierung zu verweisen.  
  
- Verwenden Sie `Handles` das-Schlüsselwort als Teil der Ereignishandlerdefinition. Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Das Hinzufügen eines Ereignis Handlers in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anfänglich analysierten Seite ist viel einfacher. Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten. Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code Behind-Datei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Seite definiert haben. Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](xaml-overview-wpf.md) oder Routing Ereignisse.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Themen zu Vorgehensweisen](events-how-to-topics.md)
