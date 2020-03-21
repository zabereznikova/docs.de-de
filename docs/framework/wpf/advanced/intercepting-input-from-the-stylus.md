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
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181917"
---
# <a name="intercepting-input-from-the-stylus"></a>Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns> Architektur bietet einen Mechanismus zum <xref:System.Windows.Input.Stylus> Implementieren von Low-Level-Steuerung über Eingaben und die Erstellung digitaler Tintenobjekte. <xref:System.Windows.Ink.Stroke> Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klasse bietet einen Mechanismus, mit dem Sie benutzerdefiniertes Verhalten implementieren und es auf den Datenstrom anwenden können, der vom Eingabestiftgerät für die optimale Leistung kommt.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Architektur](#Architecture)  
  
- [Implementieren von Stylus Plug-Ins](#ImplementingStylusPlugins)  
  
- [Hinzufügen Ihres Plug-Ins zu einem InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Aufbau  
 Dies <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist die Weiterentwicklung der [StylusInput-APIs,](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) die unter [Zugriff auf und Bearbeiten von Stifteingaben](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))beschrieben werden.  
  
 Jede <xref:System.Windows.UIElement> hat <xref:System.Windows.UIElement.StylusPlugIns%2A> eine Eigenschaft, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>ist. Sie können <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> der <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft eines Elements <xref:System.Windows.Input.StylusPoint> eine hinzufügen, um Daten beim Generieren zu bearbeiten. <xref:System.Windows.Input.StylusPoint>Daten bestehen aus allen Eigenschaften, die vom <xref:System.Windows.Input.StylusPoint.X%2A> Systemdigitizer unterstützt werden, einschließlich der und <xref:System.Windows.Input.StylusPoint.Y%2A> Punktdaten, sowie <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> Daten.  
  
 Ihre <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte werden direkt in den Datenstrom <xref:System.Windows.Input.Stylus> eingefügt, der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> vom <xref:System.Windows.UIElement.StylusPlugIns%2A> Gerät kommt, wenn Sie die der Eigenschaft hinzufügen. Die Reihenfolge, in der Plug-Ins der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung hinzugefügt werden, <xref:System.Windows.Input.StylusPoint> bestimmt die Reihenfolge, in der sie Daten empfangen. Wenn Sie z. B. ein Filter-Plug-In hinzufügen, das die Eingabe auf einen bestimmten Bereich beschränkt, und dann ein Plug-In hinzufügen, <xref:System.Windows.Input.StylusPoint> das Gesten erkennt, während sie geschrieben werden, empfängt das Plug-In, das Gesten erkennt, gefilterte Daten.  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>Implementieren von Stylus Plug-Ins  
 Um ein Plug-In zu implementieren, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>leiten Sie eine Klasse von ab. Diese Klasse wird auf den Datenstrom angewendet, <xref:System.Windows.Input.Stylus>sobald sie aus der hereinkommt. In dieser Klasse können Sie <xref:System.Windows.Input.StylusPoint> die Werte der Daten ändern.  
  
> [!CAUTION]
> Wenn <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eine Ausnahme ausgelöst oder verursacht, wird die Anwendung geschlossen. Sie sollten Steuerelemente gründlich <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> testen, die ein Steuerelement <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> verbrauchen, und nur dann ein Steuerelement verwenden, wenn Sie sicher sind, dass die keine Ausnahme auslöst.  
  
 Das folgende Beispiel veranschaulicht ein Plug-In, das die <xref:System.Windows.Input.StylusPoint.X%2A> Eingabe <xref:System.Windows.Input.StylusPoint.Y%2A> des <xref:System.Windows.Input.StylusPoint> Stifts einschränkt, <xref:System.Windows.Input.Stylus> indem die und die Werte in den Daten so geändert werden, wie sie vom Gerät hereingehen.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Hinzufügen Ihres Plug-Ins zu einem InkCanvas  
 Die einfachste Möglichkeit, Ihr benutzerdefiniertes Plug-In zu verwenden, besteht darin, eine <xref:System.Windows.UIElement.StylusPlugIns%2A> Klasse zu implementieren, die von InkCanvas abstammt, und sie der Eigenschaft hinzuzufügen.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.InkCanvas> wird eine benutzerdefinierte Datei veranschaulicht, die die Tinte filtert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie `FilterInkCanvas` ihrer Anwendung eine hinzufügen und ausführen, werden Sie feststellen, dass die Freihandeinschrift erst dann auf einen Bereich beschränkt ist, nachdem der Benutzer einen Strich abgeschlossen hat. Dies liegt <xref:System.Windows.Controls.InkCanvas> daran, dass der eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft hat, die ein <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Und-Teil der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung ist und bereits ist. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> benutzerdefinierte, <xref:System.Windows.UIElement.StylusPlugIns%2A> die Sie <xref:System.Windows.Input.StylusPoint> der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Auflistung hinzugefügt haben, empfängt die Daten, nachdem Daten empfangen wurden. Daher werden die <xref:System.Windows.Input.StylusPoint> Daten erst gefiltert, nachdem der Benutzer den Stift anhebt, um einen Strich zu beenden. Um die Tinte so zu filtern, wie `FilterPlugin` der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>Benutzer sie zeichnet, müssen Sie die vor der einfügen.  
  
 Der folgende C-Code <xref:System.Windows.Controls.InkCanvas> veranschaulicht eine benutzerdefinierte, die die Tinte beim Zeichnen filtert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Zusammenfassung  
 Wenn Sie Ihre <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eigenen Klassen ableiten <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> und in Sammlungen einfügen, können Sie das Verhalten Ihrer digitalen Tinte erheblich verbessern. Sie haben Zugriff <xref:System.Windows.Input.StylusPoint> auf die generierten Daten, sodass <xref:System.Windows.Input.Stylus> Sie die Eingabe anpassen können. Da Sie auf so niedrigem <xref:System.Windows.Input.StylusPoint> Niveau auf die Daten zugreifen können, können Sie die Farberfassung und das Rendering mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugriff auf und Manipulation von Pen-Eingängen](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
