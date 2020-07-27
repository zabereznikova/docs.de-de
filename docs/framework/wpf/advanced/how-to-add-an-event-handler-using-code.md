---
title: 'Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code'
description: Verwenden Sie dieses Beispiel, um zu erfahren, wie Sie einem Element in Windows Presentation Foundation einen Ereignishandler hinzufügen, indem Sie Code verwenden, anstatt ihn mithilfe von XAML zu deklarieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166362"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code
In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.  
  
 Wenn Sie einem-Element einen Ereignishandler hinzufügen möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen. Wenn Sie die Elementstruktur für eine Anwendung, die vollständig Code verwendet, und keine Elemente mithilfe von deklarieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , können Sie alternativ bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Controls.Button> wird einer vorhandenen Seite, die anfänglich in definiert ist, ein neues hinzugefügt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler für hinzu <xref:System.Windows.Controls.Button> .  
  
 Im c#-Beispiel wird der- `+=` Operator verwendet, um einem Ereignis einen Handler zuzuweisen. Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen. Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern. Stattdessen ist eine von zwei Methoden erforderlich:  
  
- Verwenden Sie die- <xref:System.Windows.UIElement.AddHandler%2A> Methode und einen- `AddressOf` Operator, um auf die Ereignishandlerimplementierung zu verweisen.  
  
- Verwenden Sie das- `Handles` Schlüsselwort als Teil der Ereignishandlerdefinition. Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Das Hinzufügen eines Ereignis Handlers in der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher. Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten. Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code Behind-Datei der Seite definiert haben [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) oder Routing Ereignisse.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Artikel zu Vorgehensweisen](events-how-to-topics.md)
