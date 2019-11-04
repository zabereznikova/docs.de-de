---
title: 'Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460441"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Gewusst wie: Hinzufügen eines Ereignishandlers mithilfe von Code
In diesem Beispiel wird gezeigt, wie einem Element mithilfe von Code ein Ereignishandler hinzugefügt wird.  
  
 Wenn Sie einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Element einen Ereignishandler hinzufügen möchten und die Markup Seite, die das-Element enthält, bereits geladen wurde, müssen Sie den Handler mithilfe von Code hinzufügen. Wenn Sie die Elementstruktur für eine Anwendung vollständig mit Code und ohne Deklaration von Elementen mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]aufbauen, können Sie auch bestimmte Methoden zum Hinzufügen von Ereignis Handlern zur konstruierten Elementstruktur aufzurufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird einer vorhandenen Seite, die anfänglich in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert ist, ein neues <xref:System.Windows.Controls.Button> hinzugefügt. Eine Code Behind-Datei implementiert eine Ereignishandlermethode und fügt diese Methode dann als neuen Ereignishandler auf dem <xref:System.Windows.Controls.Button>hinzu.  
  
 Im C# Beispiel wird der `+=`-Operator verwendet, um einem Ereignis einen Handler zuzuweisen. Dabei handelt es sich um denselben Operator, der verwendet wird, um einen Handler im Ereignis Behandlungsmodell Common Language Runtime (CLR) zuzuweisen. Microsoft Visual Basic unterstützt diesen Operator nicht als Mittel zum Hinzufügen von Ereignis Handlern. Stattdessen ist eine von zwei Methoden erforderlich:  
  
- Verwenden Sie die <xref:System.Windows.UIElement.AddHandler%2A>-Methode sowie einen `AddressOf`-Operator, um auf die Ereignishandlerimplementierung zu verweisen.  
  
- Verwenden Sie das `Handles`-Schlüsselwort als Teil der Ereignishandlerdefinition. Diese Technik wird hier nicht angezeigt. siehe [Visual Basic und WPF-Ereignis Behandlung](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Das Hinzufügen eines Ereignis Handlers in der anfänglich analysierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite ist viel einfacher. Fügen Sie innerhalb des Objekt Elements, dem Sie den Ereignishandler hinzufügen möchten, ein Attribut hinzu, das dem Namen des Ereignisses entspricht, das Sie behandeln möchten. Geben Sie dann den Wert dieses Attributs als Namen der Ereignishandlermethode an, die Sie in der Code-Behind-Datei der Seite "[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]" definiert haben. Weitere Informationen finden Sie unter [Übersicht über](routed-events-overview.md) [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) oder Routing Ereignisse.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Themen zu Vorgehensweisen](events-how-to-topics.md)
