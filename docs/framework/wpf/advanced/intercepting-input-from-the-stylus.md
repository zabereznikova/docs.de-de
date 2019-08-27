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
ms.openlocfilehash: 2547c0aa2f3a14080868c2760fa8999eb99d3d16
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046330"
---
# <a name="intercepting-input-from-the-stylus"></a>Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns> -Architektur bietet einen Mechanismus zum Implementieren der Steuerung auf <xref:System.Windows.Input.Stylus> niedriger Ebene für die Eingabe und die Erstellung <xref:System.Windows.Ink.Stroke> von Digital Ink-Objekten. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> -Klasse stellt einen Mechanismus bereit, mit dem Sie benutzerdefiniertes Verhalten implementieren und auf den Datenstrom des Tablettstiftgeräts anwenden können, um die optimale Leistung zu erzielen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- [Architektur](#Architecture)  
  
- [Implementieren von Tablettstift-Plug-ins](#ImplementingStylusPlugins)  
  
- [Hinzufügen des Plug-ins zu einem InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architektur  
 Bei handelt es sich um die Entwicklung der [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) -APIs, die unter [zugreifen auf und manipulieren von Stift Eingaben](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)im [Microsoft Windows XP Tablet PC Edition Software Development Kit 1,7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)beschrieben werden. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>  
  
 Jede <xref:System.Windows.UIElement> verfügt über <xref:System.Windows.UIElement.StylusPlugIns%2A> eine-Eigenschaft, <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>die eine ist. Sie können der- <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Eigenschaft eines Elements eine <xref:System.Windows.UIElement.StylusPlugIns%2A> hinzufügen, <xref:System.Windows.Input.StylusPoint> um die Daten zu bearbeiten, wenn Sie generiert werden. <xref:System.Windows.Input.StylusPoint>Daten bestehen aus allen Eigenschaften, die vom System-Digitalisierer unterstützt <xref:System.Windows.Input.StylusPoint.X%2A> werden <xref:System.Windows.Input.StylusPoint.Y%2A> , einschließlich der-und- <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> Punktdaten sowie von Daten.  
  
 Die Objekte werden direkt in den Daten <xref:System.Windows.Input.Stylus> Strom des Geräts eingefügt, wenn <xref:System.Windows.UIElement.StylusPlugIns%2A> Sie der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> -Eigenschaft hinzufügen. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Die Reihenfolge, in der Plug-Ins zur Auflistung <xref:System.Windows.UIElement.StylusPlugIns%2A> hinzugefügt werden, legt die Reihenfolge fest <xref:System.Windows.Input.StylusPoint> , in der Sie Daten erhalten. Wenn Sie z. b. ein Filter-Plug-in hinzufügen, das die Eingabe für eine bestimmte Region einschränkt, und dann ein Plug-in hinzufügen, das Gesten beim Schreiben erkennt, empfängt das Plug-in <xref:System.Windows.Input.StylusPoint> , das Gesten erkennt, gefilterte Daten.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementieren von Tablettstift-Plug-ins  
 Um ein Plug-in zu implementieren, leiten Sie eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>Klasse von ab. Diese Klasse wird auf den Datenstrom angewendet, der aus dem <xref:System.Windows.Input.Stylus>stammt. In dieser Klasse können Sie die Werte der <xref:System.Windows.Input.StylusPoint> Daten ändern.  
  
> [!CAUTION]
> Wenn eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Ausnahme auslöst oder eine Ausnahme auslöst, wird die Anwendung geschlossen. Sie sollten Steuerelemente, die einen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nutzen, gründlich testen und nur dann ein Steuerelement verwenden, wenn Sie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> sicher sind, dass keine Ausnahme auslöst.  
  
 Das folgende Beispiel veranschaulicht ein Plug-in, das die Stift Eingabe einschränkt, indem die <xref:System.Windows.Input.StylusPoint.X%2A> - <xref:System.Windows.Input.StylusPoint.Y%2A> und-Werte <xref:System.Windows.Input.StylusPoint> in den Daten vom <xref:System.Windows.Input.Stylus> Gerät geändert werden.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Hinzufügen des Plug-ins zu einem InkCanvas  
 Die einfachste Möglichkeit, Ihr benutzerdefiniertes Plug-in zu verwenden, ist die Implementierung einer Klasse, die von InkCanvas abgeleitet <xref:System.Windows.UIElement.StylusPlugIns%2A> und der-Eigenschaft hinzugefügt wird.  
  
 Das folgende Beispiel veranschaulicht eine Benutzer <xref:System.Windows.Controls.InkCanvas> definierte, die die frei Hand Eingabe filtert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie Ihrer Anwendung `FilterInkCanvas` eine hinzufügen und diese ausführen, werden Sie feststellen, dass die frei Hand Eingabe nicht auf eine Region beschränkt ist, bis der Benutzer einen Strich abschließt. Dies liegt daran, <xref:System.Windows.Controls.InkCanvas> dass die <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> über eine-Eigenschaft verfügt <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> , die ein ist und bereits ein <xref:System.Windows.UIElement.StylusPlugIns%2A> Member der-Auflistung ist. Das Benutzer <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> definierte, das Sie <xref:System.Windows.UIElement.StylusPlugIns%2A> der Auflistung hinzu <xref:System.Windows.Input.StylusPoint> gefügt haben <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> , empfängt die Daten nach dem Empfang von Daten Infolgedessen werden die <xref:System.Windows.Input.StylusPoint> Daten erst gefiltert, wenn der Benutzer den Stift zum Beenden eines Strichs anhebt. Um die frei Hand Eingaben zu filtern, während Sie vom Benutzer gezeichnet werden `FilterPlugin` , müssen <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>Sie die vor dem Einfügen.  
  
 Der folgende C# Code veranschaulicht eine Benutzer <xref:System.Windows.Controls.InkCanvas> definierte, die die frei Hand Eingabe filtert, während Sie gezeichnet wird.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Indem Sie Ihre eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen ableiten und in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> Auflistungen einfügen, können Sie das Verhalten Ihrer digitalen Handschrift erheblich verbessern. Sie haben Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, wenn Sie generiert werden, und haben die Möglichkeit, die <xref:System.Windows.Input.Stylus> Eingabe anzupassen. Da Sie über einen solchen Zugriff auf die Daten auf <xref:System.Windows.Input.StylusPoint> niedriger Ebene verfügen, können Sie die frei Hand Erfassung und das Rendering mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte Behandlung von Freihandeingaben](advanced-ink-handling.md)
- [Zugreifen auf und Bearbeiten von Stift Eingaben](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
