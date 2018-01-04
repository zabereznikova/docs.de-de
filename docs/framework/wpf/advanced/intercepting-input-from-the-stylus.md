---
title: Abfangen von Tablettstifteingaben
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5fde62e2e1ab17b26c91051f68b7d4225450c60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="intercepting-input-from-the-stylus"></a>Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns> -Architektur bietet einen Mechanismus zum Implementieren von systemnahe Steuerung über <xref:System.Windows.Input.Stylus> Eingabe und die Erstellung von Freihandeingaben <xref:System.Windows.Ink.Stroke> Objekte. Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klasse bietet einen Mechanismus für benutzerdefinierte Verhalten implementieren, und wenden Sie es in den Stream der Daten aus der Tablettstiftgerät, um eine optimale Leistung zu erzielen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Architektur](#Architecture)  
  
-   [Implementieren der Tablettstift-Plug-ins](#ImplementingStylusPlugins)  
  
-   [Hinzufügen eines Plug-Ins zu einem InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architektur  
 Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist die Weiterentwicklung der der [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) in beschriebenen APIs [zugreifen auf und Bearbeiten von Stifteingabe](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)in die [Microsoft Windows XP Tablet PC Edition-Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Jede <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.UIElement.StylusPlugIns%2A> -Eigenschaft, ist eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Können Sie Hinzufügen einer <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> auf ein Element <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft bearbeiten <xref:System.Windows.Input.StylusPoint> Daten, wie er generiert werden. <xref:System.Windows.Input.StylusPoint>Daten bestehen aus den Eigenschaften, die für die vom System Digitizer, einschließlich unterstützt die <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> zeigen Daten als auch <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> Daten.  
  
 Ihre <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Objekte eingefügt werden, direkt in den Stream der Daten aus der <xref:System.Windows.Input.Stylus> Gerät beim Hinzufügen der <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> auf die <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft. Die Reihenfolge, in der-Plug-ins hinzugefügt werden, auf, die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung bestimmt die Reihenfolge, in dem erhalten sie <xref:System.Windows.Input.StylusPoint> Daten. Z. B. Wenn Sie fügen Sie einen Filter-Plug-Ins, die Eingabe für eine bestimmte Region beschränkt, und fügen Sie dann ein plug-in, das Gesten erkennt, wie sie geschrieben werden, das plug-in, das erkennt Gesten erhalten gefilterte <xref:System.Windows.Input.StylusPoint> Daten.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementieren der Tablettstift-Plug-ins  
 Um ein plug-in zu implementieren, leiten Sie eine Klasse von <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Diese Klasse ist angewendeten o der Datenstrom der, wie sie vom stammen, der <xref:System.Windows.Input.Stylus>. In dieser Klasse können Sie die Werte der Ändern der <xref:System.Windows.Input.StylusPoint> Daten.  
  
> [!CAUTION]
>  Wenn eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eine Ausnahme auslöst oder löst eine Ausnahme, die Anwendung wird beendet. Steuerelemente, die nutzen, sollten gründlich getestet eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und ein Steuerelement nur dann verwenden, wenn Sie sicher sind die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> wird keine Ausnahme ausgelöst.  
  
 Das folgende Beispiel zeigt ein plug-in, das durch ändern die Tablettstifteingabe schränkt die <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> Werte in der <xref:System.Windows.Input.StylusPoint> Daten, wie sie eingehen aus der <xref:System.Windows.Input.Stylus> Gerät.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Hinzufügen eines Plug-Ins zu einem InkCanvas  
 Die einfachste Möglichkeit zum Verwenden benutzerdefinierter-Plug-in wird zum Implementieren von InkCanvas abgeleitete Klasse an, und fügen sie die <xref:System.Windows.UIElement.StylusPlugIns%2A> Eigenschaft.  
  
 Das folgende Beispiel zeigt ein benutzerdefiniertes <xref:System.Windows.Controls.InkCanvas> zum Filtern von Freihandeingaben.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie beim Hinzufügen einer `FilterInkCanvas` für Ihre Anwendung und ausführen, Sie werden feststellen, dass Freihandeingaben nicht auf einen Bereich beschränkt ist, nachdem der Benutzer einen Strich abgeschlossen hat. Grund hierfür ist, die <xref:System.Windows.Controls.InkCanvas> verfügt über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> Eigenschaft, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und ist bereits ein Mitglied der <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung. Die benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Sie hinzugefügt der <xref:System.Windows.UIElement.StylusPlugIns%2A> Sammlung erhält die <xref:System.Windows.Input.StylusPoint> Daten nach <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Daten empfängt. Daher die <xref:System.Windows.Input.StylusPoint> Daten werden erst nicht gefiltert, bevor der Benutzer den Stift zum Beenden eines Strichs anhebt. Sie müssen zum Filtern von Freihandeingaben wie der Benutzer es zeichnet Einfügen der `FilterPlugin` vor der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Der folgende C#-Code zeigt ein benutzerdefiniertes <xref:System.Windows.Controls.InkCanvas> zum Filtern von Freihandeingaben wie es gezeichnet wird.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Schlussbemerkung  
 Durch Ableiten von Ihren eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Klassen und Einfügen in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> Auflistungen, Sie können das Verhalten von Ihrem Freihandeingaben erheblich verbessern. Haben Sie Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, wie er generiert, mit dem Sie die Möglichkeit zum Anpassen der <xref:System.Windows.Input.Stylus> Eingabe. Schreibberechtigung für diesen Low-Level-Zugriff auf die <xref:System.Windows.Input.StylusPoint> Daten, können Sie Freihandeingaben und das Rendering mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [Zugreifen auf und Bearbeiten von Stifteingabe](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
