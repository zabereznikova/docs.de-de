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
ms.openlocfilehash: 5c22c2862ae8b948787fd5e6ca16109aa2f52aef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218770"
---
# <a name="intercepting-input-from-the-stylus"></a>Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns> Architektur bietet einen Mechanismus zum Implementieren der Steuerung auf niedriger Ebene über <xref:System.Windows.Input.Stylus> sowie die Erstellung von digitaler Tinte <xref:System.Windows.Ink.Stroke> Objekte. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> -Klasse bietet einen Mechanismus für die Sie benutzerdefiniertes Verhalten implementieren, und klicken Sie auf die vom Tablettstift für eine optimale Leistung eingehenden Datenstrom anzuwenden.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Architektur](#Architecture)  
  
-   [Implementieren der Tablettstift-Plug-ins](#ImplementingStylusPlugins)  
  
-   [Hinzufügen eines Plug-Ins an ein InkCanvas-Steuerelement](#AddingYourPluginToAnInkCanvas)  
  
-   [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architektur  
 Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist die Weiterentwicklung von der [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) APIs, die in beschriebenen [zugreifen auf und Bearbeiten von Stifteingabe](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)in die [Microsoft Windows XP Tablet PC Edition-Software Development Kit 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Jede <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.UIElement.StylusPlugIns%2A> -Eigenschaft, ist eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Hinzufügbaren eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> auf ein Element des <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft bearbeiten <xref:System.Windows.Input.StylusPoint> Daten generiert werden. <xref:System.Windows.Input.StylusPoint> Daten besteht aus den Eigenschaften, die für die vom System Digitizer, einschließlich unterstützt die <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> zeigen Daten als auch <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> Daten.  
  
 Ihre <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte eingefügt werden, direkt in den Stream der Daten aus der <xref:System.Windows.Input.Stylus> Gerät beim Hinzufügen der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> auf die <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft. Die Reihenfolge in der-Plug-ins, um hinzugefügt werden die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung bestimmt die Reihenfolge, in dem sie erhalten <xref:System.Windows.Input.StylusPoint> Daten. Z. B. Wenn Sie fügen Sie einen Filter-Plug-Ins, die Eingabe für eine bestimmte Region beschränkt, und fügen Sie dann ein plug-in, das erkennt Bewegungen, wie sie geschrieben werden, das plug-in, das erkennt Bewegungen erhalten gefilterte <xref:System.Windows.Input.StylusPoint> Daten.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementieren der Tablettstift-Plug-ins  
 Um ein plug-in zu implementieren, leiten Sie eine Klasse von <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Diese Klasse ist angewendeten o des Datenstroms, stammt von die <xref:System.Windows.Input.Stylus>. In dieser Klasse können Sie ändern die Werte der <xref:System.Windows.Input.StylusPoint> Daten.  
  
> [!CAUTION]
>  Wenn eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> auslöst, oder löst eine Ausnahme, die Anwendung wird beendet. Steuerelemente, die nutzen, sollten gründlich getestet eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und nur ein Steuerelement verwenden, wenn Sie sicher sind die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> wird keine Ausnahme ausgelöst.  
  
 Das folgende Beispiel zeigt ein plug-in, das schränkt die nastala chyba vstupu durch Ändern der <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> Werte in der <xref:System.Windows.Input.StylusPoint> Daten stammen der <xref:System.Windows.Input.Stylus> Gerät.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Hinzufügen eines Plug-Ins an ein InkCanvas-Steuerelement  
 Die einfachste Möglichkeit zum Verwenden benutzerdefinierter-Plug-in wird zum Implementieren einer Klasse, die von InkCanvas-Steuerelement abgeleitet wird, und fügen sie der <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft.  
  
 Das folgende Beispiel veranschaulicht eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas> zum Filtern von Freihandeingaben.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie beim Hinzufügen einer `FilterInkCanvas` zu Ihrer Anwendung und führen Sie es, Sie werden feststellen, dass die Freihandeingaben beschränkt, in einer Region, bis der Benutzer einen Strich abgeschlossen hat. Grund hierfür ist, die <xref:System.Windows.Controls.InkCanvas> verfügt über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und bereits ein Mitglied der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Die benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Sie hinzugefügt haben, um die <xref:System.Windows.UIElement.StylusPlugIns%2A> Sammlung erhält die <xref:System.Windows.Input.StylusPoint> Daten nach <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> empfängt Daten. Daher die <xref:System.Windows.Input.StylusPoint> Daten nicht gefiltert werden, erst nach dem der Benutzer den Stift zum Beenden eines Strichs anhebt. Um, wenn der Benutzer es zeichnet die Freihandeingabe zu filtern, müssen Sie das Einfügen der `FilterPlugin` vor der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Der folgende C#-Code veranschaulicht eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas> , filtert die Freihandeingabe, wie es gezeichnet wird.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Durch Ableiten von Ihren eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen und Einfügen in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> Auflistungen, Sie können das Verhalten von digitaler Tinte erheblich verbessern. Sie haben Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten generiert, haben Sie die Möglichkeit zum Anpassen der <xref:System.Windows.Input.Stylus> Eingabe. Da diesen Low-Level-Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, Sie können die Freihandeingaben und das Rendering mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugreifen auf und Bearbeiten von Stifteingabe](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
