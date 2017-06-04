---
title: "Abfangen von Tablettstifteingaben | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Architektur, System.Windows.Input.StylusPlugIns"
  - "InkCanvas, Hinzufügen von Plug-Ins zu"
  - "Plug-Ins, Tablettstift"
  - "StylusPlugIns-Architektur"
  - "System.Windows.Input.StylusPlugIns-Architektur"
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Abfangen von Tablettstifteingaben
Die <xref:System.Windows.Input.StylusPlugIns>\-Architektur stellt einen Mechanismus zum Implementieren einer Low\-Level\-Steuerung von <xref:System.Windows.Input.Stylus>\-Eingaben und zum Erstellen von <xref:System.Windows.Ink.Stroke> \-Objekten für die digitale Freihandeingabe bereit.  Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Klasse stellt Ihnen einen Mechanismus zur Verfügung, um benutzerdefiniertes Verhalten zu implementieren und dieses für eine optimale Leistung auf den vom Tablettstift eingehenden Datenstrom anzuwenden.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   [Architektur](#Architecture)  
  
-   [Implementieren von Tablettstift-Plug-Ins](#ImplementingStylusPlugins)  
  
-   [Hinzufügen eines Plug-Ins zu einem InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Schlussfolgerung](#Conclusion)  
  
<a name="Architecture"></a>   
## Architektur  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ist die Weiterentwicklung der [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409)\-APIs, erläutert in [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409) im [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Jedes <xref:System.Windows.UIElement> verfügt über eine <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Eigenschaft, die eine <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ist.  Sie können ein <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> zur <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Eigenschaft eines Elements hinzufügen, um die <xref:System.Windows.Input.StylusPoint>\-Daten beim Erzeugen zu bearbeiten.  <xref:System.Windows.Input.StylusPoint>\-Daten enthalten alle Eigenschaften, die vom Systemdigitalisierungsgerät unterstützt werden, einschließlich der Punktdaten <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> sowie der <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>\-Daten.  
  
 Die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Objekte werden direkt in den vom <xref:System.Windows.Input.Stylus>\-Gerät eingehenden Datenstrom eingefügt, wenn Sie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> zur <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Eigenschaft hinzufügen.  Die Reihenfolge, in der Plug\-Ins zur <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung hinzugefügt werden, entscheidet über die Reihenfolge, in der sie <xref:System.Windows.Input.StylusPoint>\-Daten empfangen.  Wenn Sie beispielsweise ein Filter\-Plug\-In hinzufügen, das die Eingabe auf einen bestimmten Bereich einschränkt, und anschließend ein Plug\-In hinzufügen, das Stiftbewegungen beim Schreiben erkennt, wird das zweite Plug\-In gefilterte <xref:System.Windows.Input.StylusPoint>\-Daten empfangen.  
  
<a name="ImplementingStylusPlugins"></a>   
## Implementieren von Tablettstift\-Plug\-Ins  
 Leiten Sie eine Klasse von <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ab, um ein Plug\-In zu implementieren.  Diese Klasse wird auf den Datenstrom angewendet, während dieser von <xref:System.Windows.Input.Stylus> bereitgestellt wird.  In dieser Klasse können Sie die Werte der <xref:System.Windows.Input.StylusPoint>\-Daten ändern.  
  
> [!CAUTION]
>  Wenn ein <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> eine Ausnahme auslöst oder verursacht, wird die Anwendung beendet.  Sie sollten Steuerelemente gründlich testen, die <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> verwenden, und ein Steuerelement nur dann verwenden, wenn Sie sicher sind, dass <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> keine Ausnahme auslösen wird.  
  
 Im folgenden Beispiel wird ein Plug\-In dargestellt, das die Tablettstifteingabe einschränkt, indem die Werte für <xref:System.Windows.Input.StylusPoint.X%2A> und <xref:System.Windows.Input.StylusPoint.Y%2A> in den <xref:System.Windows.Input.StylusPoint> Daten geändert werden, während sie vom <xref:System.Windows.Input.Stylus>\-Gerät bereitgestellt werden.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## Hinzufügen eines Plug\-Ins zu einem InkCanvas  
 Die einfachste Möglichkeit zum Verwenden benutzerdefinierter Plug\-Ins besteht im Implementieren einer von InkCanvas abgeleiteten Klasse und dem Hinzufügen zur <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Eigenschaft.  
  
 Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas>\-Klasse zum Filtern von Freihandeingaben dargestellt.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Wenn Sie ein `FilterInkCanvas` Ihrer Anwendung hinzufügen und diese ausführen, werden Sie feststellen, dass die Freihandeingaben nicht auf einen Bereich eingeschränkt werden, bevor der Benutzer einen Strich abgeschlossen hat.  Dies geschieht, weil <xref:System.Windows.Controls.InkCanvas> über eine <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>\-Eigenschaft verfügt, bei der es sich um ein <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> handelt, das bereits ein Member der <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung ist.  Das benutzerdefinierte <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, das Sie der <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung hinzugefügt haben, empfängt die <xref:System.Windows.Input.StylusPoint>\-Daten, nachdem <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> Daten empfangen hat.  Daraus folgt, dass die <xref:System.Windows.Input.StylusPoint>\-Daten nicht gefiltert werden, bevor der Benutzer den Stift anhebt, um einen Strich abzuschließen.  Um die Freihandeingabe bereits während des Zeichnens durch den Benutzer zu filtern, müssen Sie das `FilterPlugin` vor dem <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> einfügen.  
  
 Im folgenden C\#\-Code wird eine benutzerdefinierte <xref:System.Windows.Controls.InkCanvas>\-Klasse dargestellt, die die Freihandeingabe während des Zeichnens filtert.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## Schlussfolgerung  
 Durch Ableiten Ihrer eigenen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>\-Klassen und deren Einfügen in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>\-Auflistungen können Sie das Verhalten von digitalen Freihandeingaben wesentlich erweitern.  Sie können bereits bei der Erstellung auf die <xref:System.Windows.Input.StylusPoint>\-Daten zugreifen und daher die <xref:System.Windows.Input.Stylus>\-Eingabe anpassen.  Durch diesen Low\-Level\-Zugriff auf die <xref:System.Windows.Input.StylusPoint>\-Daten können Sie das Erfassen und Rendern von Freihandeingaben mit optimaler Leistung für Ihre Anwendung implementieren.  
  
## Siehe auch  
 [Erweiterte Behandlung von Freihandeingaben](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Zugriff auf Stifteingaben und Bearbeiten von Stifteingaben](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)