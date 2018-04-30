---
title: 'Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 06a2c2049ec7fe7046bd6dae2711fe8e46592fcf
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF

Es gibt im Wesentlichen drei Plattformen, die Freihandeingaben unterstützen: die Tablet PC Windows Forms-Plattform, die Tablet PC COM-Plattform und die Plattform Windows Presentation Foundation (WPF).  Die Freigabe für Windows Forms und COM-Plattformen ein ähnliches Objektmodell jedoch stattdessen das Modell für die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Plattform unterscheidet sich deutlich.  Dieses Thema erläutert die Unterschiede auf hoher Ebene, damit Entwickler, die mit einem Objektmodell gearbeitet haben, können die anderen besser verstehen.  
  
## <a name="enabling-ink-in-an-application"></a>Aktivieren von Freihandeingaben in einer Anwendung  
 Alle drei Plattformen enthalten Objekte und Steuerelemente, die eine Anwendung zum Empfangen von Eingaben von einem Tablettstift zu aktivieren.  Die Windows Forms und COM-Plattformen sind im Lieferumfang [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) und [ Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) Klassen.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) und [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) sind Steuerelemente, die Sie hinzufügen können, um eine Anwendung zum Erfassen von Freihandeingaben.  Die [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) und [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) an ein vorhandenes Fenster an Freihand-Enable-Fenstern und benutzerdefinierten Steuerelementen angefügt werden können.  
  
 Die WPF-Plattform umfasst die <xref:System.Windows.Controls.InkCanvas> Steuerelement.  Sie können Hinzufügen einer <xref:System.Windows.Controls.InkCanvas> für Ihre Anwendung und sofort Freihandeingaben erfassen. Mit der <xref:System.Windows.Controls.InkCanvas>, der Benutzer kann zu kopieren, wählen Sie und Freihandeingaben Größe.  Sie können andere Steuerelemente zum Hinzufügen der <xref:System.Windows.Controls.InkCanvas>, und der Benutzer kann über die Steuerelemente zu Handschrift.  Sie können ein Freihandeingaben benutzerdefiniertes Steuerelement erstellen, durch Hinzufügen einer <xref:System.Windows.Controls.InkPresenter> Anforderung und Sammeln von seiner Tablettstiftpunkte.  
  
 Die folgende Tabelle enthält, wo Sie weitere Informationen zum Aktivieren von Freihandeingaben in einer Anwendung:  
  
|Zu diesem Zweck...|Auf der WPF-Plattform...|Auf den Windows Forms/COM-Plattformen...|  
|-----------------|--------------------------|------------------------------------------|  
|Hinzufügen eines Steuerelements Freihandeingaben zu einer Anwendung|Finden Sie unter [Getting Started with Ink](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Finden Sie unter [automatisch Ansprüche bilden, Beispiel](http://msdn.microsoft.com/bec4333a-62ca-4254-a39b-04bc2c556992)|  
|Ermöglichen von Freihandeingaben in ein benutzerdefiniertes Steuerelement|Finden Sie unter [Steuerelement erstellen ein Freihand Eingabe](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Finden Sie unter [Freihand-Zwischenablage-Beispiel](http://msdn.microsoft.com/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## <a name="ink-data"></a>Freihanddaten  
 Auf der Windows Forms- und COM-Plattformen [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), und [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) jedes machen eine [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) Objekt. Die [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) Objekt enthält die Daten für eine oder mehrere [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) -Objekte und stellt allgemeine Methoden und Eigenschaften dieser Striche zu verwalten.  Die [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) -Objekt verwaltet die Lebensdauer der Striche enthält, die [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) Objekt erstellt und löscht die Striche, die er besitzt.  Jede [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) verfügt über einen Bezeichner, der in seinem übergeordneten Element eindeutig ist [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) Objekt.  
  
 Auf der WPF-Plattform die <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> Klasse besitzt und verwaltet eine eigene Lebensdauer. Eine Gruppe von <xref:System.Windows.Ink.Stroke> Objekte können zusammen gesammelt werden, einem <xref:System.Windows.Ink.StrokeCollection>, Methoden für allgemeine Freihand-Datenverwaltungsvorgänge wie z. B. stellt testen, löschen, Transformieren und Serialisieren Freihandeingaben erreicht. Ein <xref:System.Windows.Ink.Stroke> kann auf 0 (null), ein oder mehrere gehören <xref:System.Windows.Ink.StrokeCollection> Objekte auf einer erteilen Zeit.  Anstatt eine [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) -Objekt, das <xref:System.Windows.Controls.InkCanvas> und <xref:System.Windows.Controls.InkPresenter> enthalten eine <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 Die folgenden zwei Abbildungen vergleicht die Freihand-Datenmodelle-Objekt.  Auf dem Windows Forms und COM-Plattformen die [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) Objekt schränkt die Lebensdauer der [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) Objekte und gehören zu den einzelnen Strichen Tablettstiftpakete.  Zwei oder mehr Striche können verweisen, die gleiche [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) -Objekts, wie in der folgenden Abbildung dargestellt.  
  
 ![Diagramm des Freihandeingabe-Objektmodells für COM-&#47;Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die jeweils <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> ist ein Objekt von common Language Runtime, die vorhanden ist, als ein Element einen Verweis darauf verfügt.  Jede <xref:System.Windows.Ink.Stroke> Verweise ein <xref:System.Windows.Input.StylusPointCollection> und <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> -Objekt, das common Language Runtime-Objekte ebenfalls enthalten sind.  
  
 ![Diagramm des Freihandeingabe-Objektmodells für WPF. ] (../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Die folgende Tabelle vergleicht, wie einige häufige Aufgaben auf der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plattform und die Plattformen Windows Forms und COM.  
  
|Aufgabe|Windows Presentation Foundation|Windows Forms und COM|  
|----------|-------------------------------------|---------------------------|  
|Freihandeingaben speichern|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Freihandeingaben laden|Erstellen einer <xref:System.Windows.Ink.StrokeCollection> mit der <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> Konstruktor.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Treffertests|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Freihand kopieren|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Fügen Sie Freihandeingaben|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Zugriff auf benutzerdefinierte Eigenschaften für eine Sammlung von Konturen|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (die Eigenschaften werden intern gespeichert und Zugriff erfolgt über <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, und <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Verwendung [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Freigeben von verschiedenen Plattformen Freihandeingaben  
 Obwohl die Plattformen unterschiedliche Objektmodelle für die Freihanddaten verfügen, ist die Freigabe von Daten zwischen den Plattformen sehr einfach. In den folgenden Beispielen Freihandeingaben aus einer Windows Forms-Anwendung gespeichert und in einer Windows Presentation Foundation-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 In den folgenden Beispielen Freihandeingaben aus einer Windows Presentation Foundation-Anwendung gespeichert und in einer Windows Forms-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Ereignisse aus den Tablettstift  
 Die [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), und [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) auf dem Windows Forms und COM-Plattformen Ereignisse empfangen werden bei der Benutzer Eingaben pen-Daten.  Die [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) oder [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) für ein Fenster oder ein Steuerelement angefügt ist, und die von der Tabletteingabedaten ausgelösten Ereignisse abonnieren können.  Der Thread, auf dem diese Ereignisse aufgetreten, hängt davon ab, ob die Ereignisse, mit einem Stift, Maus ausgelöst werden, oder programmgesteuert.  Weitere Informationen zu threading in Bezug auf diese Ereignisse finden Sie unter [Allgemeines Threading](http://msdn.microsoft.com/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) und [Threads auf dem ein Ereignis ausgelöst werden kann](http://msdn.microsoft.com/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 Auf der Windows Presentation Foundation-Plattform die <xref:System.Windows.UIElement> -Klasse verfügt über die Ereignisse für Stifteingabe. Dies bedeutet, dass jedes Steuerelement den vollständigen Satz von Stylus-Ereignisse verfügbar macht.  Die Stiftereignisse haben Ereignis tunneling/bubbling-Paare und immer für den Thread der Anwendung ausgeführt.  Weitere Informationen finden Sie unter [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Das folgende Diagramm zeigt vergleicht die Objektmodelle für die Klassen, die Stylus-Ereignisse auslösen. Das Objektmodell von Windows Presentation Foundation zeigt nur die bubbling Ereignisse nicht die Tunneling-Ereignis-Entsprechungen.  
  
 ![Diagramm der Stylus-Ereignisse in WPF im Vergleich zu Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Pen-Daten  
 Alle drei Plattformen bieten Möglichkeiten, abzufangen und bearbeiten die Daten, die in einem Tablettstift stammen.  Auf der Windows Forms- und COM-Plattformen, dies erfolgt durch Erstellen einer [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx), einem Fenster- oder Steuerelement zuordnen und erstellen Sie eine Klasse, implementiert der [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) oder [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) Schnittstelle. Das benutzerdefinierte plug-in wird dann hinzugefügt, auf die Plug-in-Auflistung von der [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Weitere Informationen über dieses Objektmodell finden Sie unter [Architektur der StylusInput APIs](http://msdn.microsoft.com/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 Auf der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plattform, die <xref:System.Windows.UIElement> Klasse macht eine Auflistung von-Plug-ins, ähnlich wie in der Entwurfsansicht auf die [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Zum Abfangen von Daten erstellen Sie eine Klasse, die von erben <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und fügen Sie das Objekt, das die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung von der <xref:System.Windows.UIElement>. Weitere Informationen zu dieser Aktivität finden Sie unter [abfangen Eingabe des Tablettstifts](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 Auf allen Plattformen werden ein Threadpool die Freihanddaten über Stylus-Ereignisse empfängt und sendet sie an Thread der Anwendung.  Weitere Informationen zu den für die Windows-Plattformen, COM threading, finden Sie unter [Threading Überlegungen für die StylusInput APIs](http://msdn.microsoft.com/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Weitere Informationen zu threading in der Windows Presentation Software finden Sie unter [Ink Threading Model](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 Die folgende Abbildung vergleicht die Objektmodelle für die Klassen, die Daten der Stift im Threadpool Stift empfangen.  
  
 ![Diagramm des StylusPlugIn-Modells WPF im Vergleich Winforms. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")
