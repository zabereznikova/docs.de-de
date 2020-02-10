---
title: Abfangen von Tablettstifteingaben
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095137"
---
# <a name="intercepting-input-from-the-stylus"></a>Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns>-Architektur bietet einen Mechanismus, mit dem die Steuerung auf niedriger Ebene für <xref:System.Windows.Input.Stylus> Eingaben und die Erstellung von digitalen Ink-<xref:System.Windows.Ink.Stroke> Objekten implementiert werden. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>-Klasse stellt einen Mechanismus bereit, mit dem Sie benutzerdefiniertes Verhalten implementieren und auf den Datenstrom des Tablettstiftgeräts anwenden können, um die optimale Leistung zu erzielen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Aufbau](#Architecture)  
  
- [Implementieren von Tablettstift-Plug-ins](#ImplementingStylusPlugins)  
  
- [Hinzufügen des Plug-ins zu einem InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Fazit](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Aufbau  
 Der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist die Entwicklung der [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) -APIs, die unter [zugreifen auf und manipulieren von Stift Eingaben](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))beschrieben werden.  
  
 Jede <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft, die <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>ist. Sie können der <xref:System.Windows.UIElement.StylusPlugIns%2A>-Eigenschaft eines Elements eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> hinzufügen, um <xref:System.Windows.Input.StylusPoint> Daten zu bearbeiten, während Sie generiert werden. <xref:System.Windows.Input.StylusPoint> Daten bestehen aus allen Eigenschaften, die vom System-Digitalisierer unterstützt werden, einschließlich der <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> Punktdaten sowie <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> Daten.  
  
 Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte werden direkt in den Datenstrom des <xref:System.Windows.Input.Stylus> Geräts eingefügt, wenn Sie die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> der <xref:System.Windows.UIElement.StylusPlugIns%2A>-Eigenschaft hinzufügen. Die Reihenfolge, in der Plug-ins der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung hinzugefügt werden, legt die Reihenfolge fest, in der Sie <xref:System.Windows.Input.StylusPoint> Daten erhalten. Wenn Sie z. b. ein Filter-Plug-in hinzufügen, das die Eingabe für eine bestimmte Region einschränkt, und dann ein Plug-in hinzufügen, das Gesten beim Schreiben erkennt, empfängt das Plug-in, das Gesten erkennt, gefilterte <xref:System.Windows.Input.StylusPoint> Daten.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementieren von Tablettstift-Plug-ins  
 Um ein Plug-in zu implementieren, leiten Sie eine Klasse von <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>ab. Diese Klasse wird auf den Datenstrom angewendet, der aus der <xref:System.Windows.Input.Stylus>stammt. In dieser Klasse können Sie die Werte der <xref:System.Windows.Input.StylusPoint> Daten ändern.  
  
> [!CAUTION]
> Wenn eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eine Ausnahme auslöst oder auslöst, wird die Anwendung geschlossen. Sie sollten Steuerelemente, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nutzen, gründlich testen und nur dann ein Steuerelement verwenden, wenn Sie sicher sind, dass die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> keine Ausnahme auslöst.  
  
 Das folgende Beispiel zeigt ein Plug-in, das die Tablettstifteingabe einschränkt, indem Sie die <xref:System.Windows.Input.StylusPoint.X%2A>-und <xref:System.Windows.Input.StylusPoint.Y%2A> Werte in den <xref:System.Windows.Input.StylusPoint> Daten ändert, wie Sie vom <xref:System.Windows.Input.Stylus>-Gerät stammen.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Hinzufügen des Plug-ins zu einem InkCanvas  
 Die einfachste Möglichkeit, Ihr benutzerdefiniertes Plug-in zu verwenden, ist die Implementierung einer Klasse, die von InkCanvas abgeleitet ist und der <xref:System.Windows.UIElement.StylusPlugIns%2A>-Eigenschaft hinzugefügt wird.  
  
 Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas> veranschaulicht, die die frei Hand Eingabe filtert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie Ihrer Anwendung eine `FilterInkCanvas` hinzufügen und diese ausführen, werden Sie feststellen, dass die frei Hand Eingabe nicht auf eine Region beschränkt ist, bis der Benutzer einen Strich abschließt. Dies liegt daran, dass die <xref:System.Windows.Controls.InkCanvas> eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>-Eigenschaft aufweist, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist und bereits ein Member der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung ist. Der benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, den Sie der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung hinzugefügt haben, empfängt die <xref:System.Windows.Input.StylusPoint> Daten, nachdem <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Daten empfangen hat. Folglich werden die <xref:System.Windows.Input.StylusPoint> Daten erst gefiltert, wenn der Benutzer den Stift zum Beenden eines Strichs anhebt. Um die frei Hand Eingaben zu filtern, während Sie vom Benutzer gezeichnet werden, müssen Sie die `FilterPlugin` vor dem <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>einfügen.  
  
 Der folgende C# Code veranschaulicht eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas>, die die frei Hand Eingabe filtert, während Sie gezeichnet wird.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Zusammenfassung  
 Indem Sie Ihre eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen ableiten und in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> Auflistungen einfügen, können Sie das Verhalten Ihrer digitalen Handschrift erheblich verbessern. Sie haben Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, wenn Sie generiert werden, und bieten Ihnen die Möglichkeit, die <xref:System.Windows.Input.Stylus> Eingaben anzupassen. Da Sie einen solchen Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten auf niedriger Ebene haben, können Sie die frei Hand Erfassung und das Rendering mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugreifen auf und Bearbeiten von Stift Eingaben](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
