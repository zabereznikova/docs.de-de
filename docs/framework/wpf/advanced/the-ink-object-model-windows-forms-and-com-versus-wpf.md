---
title: "Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF | Microsoft Docs"
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
  - "Aktivieren von Freihandeingaben"
  - "Ereignisse, Tablettstift"
  - "Freihandeingaben-Objektmodell"
  - "Freihandeingaben, Aktivieren"
  - "InkCanvas-Steuerelement"
  - "Tablettstift, Ereignisse"
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF
Es gibt im Prinzip drei Plattformen, die Freihandeingaben unterstützen: die Tablet PC Windows Forms\-Plattform, die Tablet PC COM\-Plattform und die [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Plattform.  Die Windows Forms\- und die COM\-Plattform haben ein ähnliches Objektmodell gemeinsam, das Objektmodell der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plattform unterscheidet sich jedoch wesentlich.  In diesem Thema werden die Unterschiede allgemein erläutert, damit Entwickler, die bereits mit einem Objektmodell gearbeitet haben, das andere besser verstehen können.  
  
## Ermöglichen von Freihandeingaben in einer Anwendung  
 Alle drei Plattformen enthalten Objekte und Steuerelemente, die es einer Anwendung ermöglichen, Eingaben von einem Tablettstift zu empfangen.  Die Windows Forms\- und die COM\-Plattform enthalten die Klassen <xref:Microsoft.Ink.InkPicture>, <xref:Microsoft.Ink.InkEdit>, <xref:Microsoft.Ink.InkOverlay> und <xref:Microsoft.Ink.InkCollector>.  Das <xref:Microsoft.Ink.InkPicture>\-Steuerelement und das <xref:Microsoft.Ink.InkEdit>\-Steuerelement können einer Anwendung zum Erfassen von Freihandeingaben hinzugefügt werden.  <xref:Microsoft.Ink.InkOverlay> und <xref:Microsoft.Ink.InkCollector> können an ein vorhandenes Fenster angefügt werden, um Freihandeingaben in Fenstern und benutzerdefinierten Steuerelementen zu ermöglichen.  
  
 Die WPF\-Plattform enthält das <xref:System.Windows.Controls.InkCanvas>\-Steuerelement.  Sie können Ihrer Anwendung ein <xref:System.Windows.Controls.InkCanvas>\-Steuerelement hinzufügen und sofort Freihandeingaben erfassen.  Mit <xref:System.Windows.Controls.InkCanvas> kann der Benutzer Freihandeingaben kopieren, auswählen und deren Größe ändern.  Sie können <xref:System.Windows.Controls.InkCanvas> weitere Steuerelemente hinzufügen. Der Benutzer kann auch über diese Steuerelemente handschriftliche Eingaben vornehmen.  Sie können ein benutzerdefiniertes Steuerelement für Freihandeingaben erstellen, indem Sie dem Steuerelement <xref:System.Windows.Controls.InkPresenter> hinzufügen und die Tablettstiftpunkte erfassen.  
  
 In der folgenden Tabelle ist aufgeführt, wo Sie mehr Informationen zum Ermöglichen von Freihandeingaben in einer Anwendung finden:  
  
|Aktion|Auf der WPF\-Plattform…|Auf der Windows Forms\- \/ COM\-Plattform…|  
|------------|-----------------------------|------------------------------------------------|  
|Hinzufügen eines Steuerelements für Freihandeingaben zu einer Anwendung|Weitere Informationen finden Sie unter [Erste Schritte mit Freihandeingaben](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Weitere Informationen finden Sie unter [Auto Claims Form Sample](http://msdn.microsoft.com/de-de/bec4333a-62ca-4254-a39b-04bc2c556992).|  
|Ermöglichen von Freihandeingaben in einem benutzerdefinierten Steuerelement|Weitere Informationen finden Sie unter [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Weitere Informationen finden Sie unter [Ink Clipboard Sample](http://msdn.microsoft.com/de-de/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## Freihanddaten  
 Auf der Windows Forms\- und der COM\-Plattform machen <xref:Microsoft.Ink.InkCollector>, <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkEdit> und <xref:Microsoft.Ink.InkPicture> jeweils ein <xref:Microsoft.Ink.Ink?displayProperty=fullName>\-Objekt verfügbar.  Das <xref:Microsoft.Ink.Ink>\-Objekt enthält die Daten für mindestens ein <xref:Microsoft.Ink.Stroke?displayProperty=fullName>\-Objekt und macht allgemeine Methoden und Eigenschaften zum Verwalten und Ändern dieser Striche verfügbar.  Das <xref:Microsoft.Ink.Ink>\-Objekt verwaltet die Lebensdauer der enthaltenen Striche. Das <xref:Microsoft.Ink.Ink>\-Objekt erstellt und löscht die Striche, deren Besitzer es ist.  Jedes <xref:Microsoft.Ink.Stroke>\-Objekt verfügt über einen Bezeichner, der innerhalb des übergeordneten <xref:Microsoft.Ink.Ink>\-Objekts eindeutig ist.  
  
 Auf der WPF\-Plattform besitzt und verwaltet die <xref:System.Windows.Ink.Stroke?displayProperty=fullName>\-Klasse ihre eigene Lebensdauer.  Eine Gruppe von <xref:System.Windows.Ink.Stroke>\-Objekten kann in einer <xref:System.Windows.Ink.StrokeCollection>\-Auflistung zusammengefasst werden, die Methoden für allgemeine Verwaltungsvorgänge für Freihanddaten bereitstellt, z. B. Trefferüberprüfung, Löschen, Umwandeln und Serialisieren von Freihandeingaben.  Ein <xref:System.Windows.Ink.Stroke> kann zu jedem Zeitpunkt zu keinem, einem oder mehreren <xref:System.Windows.Ink.StrokeCollection>\-Objekten gehören.  Anstelle eines <xref:Microsoft.Ink.Ink?displayProperty=fullName>\-Objekts können <xref:System.Windows.Controls.InkCanvas> und <xref:System.Windows.Controls.InkPresenter> ein <xref:System.Windows.Ink.StrokeCollection?displayProperty=fullName>\-Objekt enthalten.  
  
 In den folgenden beiden Abbildungen werden die Freihanddaten\-Objektmodelle miteinander verglichen.  Auf der Windows Forms\- und der COM\-Plattform schränkt das <xref:Microsoft.Ink.Ink?displayProperty=fullName>\-Objekt die Lebensdauer der <xref:Microsoft.Ink.Stroke?displayProperty=fullName>\-Objekte ein, und die Tablettstiftpakete gehören zu den einzelnen Strichen.  Zwei oder mehr Striche können auf dasselbe <xref:Microsoft.Ink.DrawingAttributes?displayProperty=fullName>\-Objekt verweisen, wie in der folgenden Abbildung dargestellt.  
  
 ![Diagramm des Freihandeingabe&#45;Objektmodells für COM&#47;Winforms.](../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink\_InkOwnsStrokes")  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist jedes <xref:System.Windows.Ink.Stroke?displayProperty=fullName>\-Objekt ein Common Language Runtime\-Objekt, das existiert, so lange ein Verweis darauf vorhanden ist.  Jedes <xref:System.Windows.Ink.Stroke>\-Objekt verweist auf ein <xref:System.Windows.Input.StylusPointCollection>\-Objekt und ein <xref:System.Windows.Ink.DrawingAttributes?displayProperty=fullName>\-Objekt, die ebenfalls Common Language Runtime\-Objekte sind.  
  
 ![Diagramm des Freihandeingabe&#45;Objektmodells für WPF.](../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink\_WPFInkObjectModel")  
  
 In der folgenden Tabelle wird verglichen, wie einige häufige Aufgaben auf der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plattform und auf der Windows Forms\- und COM\-Plattform durchgeführt werden.  
  
|Aufgabe|Windows Presentation Foundation|Windows Forms und COM|  
|-------------|-------------------------------------|---------------------------|  
|Freihandeingabe speichern|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|<xref:Microsoft.Ink.Ink.Save%2A>|  
|Freihandeingabe laden|Erstellen Sie ein <xref:System.Windows.Ink.StrokeCollection>\-Objekt mit dem <xref:System.Windows.Ink.StrokeCollection.%23ctor%28System.IO.Stream%29?displayProperty=fullName>\-Konstruktor.|[M:Microsoft.Ink.Ink.Load\(System.Byte\<xref:Microsoft.Ink.Ink.Load%2A>|  
|Trefferüberprüfung|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|<xref:Microsoft.Ink.Ink.HitTest%2A>|  
|Freihandeingabe kopieren|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|<xref:Microsoft.Ink.Ink.ClipboardCopy%2A>|  
|Freihandeingabe einfügen|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|<xref:Microsoft.Ink.Ink.ClipboardPaste%2A>|  
|Zugriff auf benutzerdefinierte Eigenschaften in einer Auflistung von Strichen|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> \(Die Eigenschaften werden intern gespeichert, der Zugriff erfolgt über <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A> und <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>.\)|Verwenden Sie <xref:Microsoft.Ink.Ink.ExtendedProperties%2A>.|  
  
### Gemeinsames Verwenden von Freihandeingaben auf verschiedenen Plattformen  
 Obwohl die Plattformen unterschiedliche Objektmodelle für die Freihanddaten haben, ist das gemeinsame Verwenden der Daten auf verschiedenen Plattformen sehr einfach.  In den folgenden Beispielen werden Freihandeingaben aus einer Windows Forms\-Anwendung gespeichert und in einer WPF \(Windows Presentation Foundation\)\-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 In den folgenden Beispielen werden Freihandeingaben aus einer WPF\-Anwendung gespeichert und in einer Windows Forms\-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]  
  
## Ereignisse vom Tablettstift  
 Auf der Windows Forms\- und der COM\-Plattform empfangen <xref:Microsoft.Ink.InkOverlay>, <xref:Microsoft.Ink.InkCollector> und <xref:Microsoft.Ink.InkPicture> Ereignisse, wenn der Benutzer Stiftdaten eingibt.  <xref:Microsoft.Ink.InkOverlay> oder <xref:Microsoft.Ink.InkCollector> wird an ein Fenster oder Steuerelement angefügt und kann die Ereignisse abonnieren, die von den Tabletteingabedaten ausgelöst werden.  In welchem Thread diese Ereignisse auftreten, hängt davon ab, ob die Ereignisse mit einem Stift, einer Maus oder programmgesteuert ausgelöst werden.  Weitere Informationen zu Threading in Bezug auf diese Ereignisse finden Sie unter [General Threading Considerations](http://msdn.microsoft.com/de-de/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) und [Threads on Which an Event Can Fire](http://msdn.microsoft.com/de-de/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 Auf der WPF\-Plattform enthält die <xref:System.Windows.UIElement>\-Klasse Ereignisse für Stifteingaben.  Dies bedeutet, dass jedes Steuerelement den vollständigen Satz von Tablettstiftereignissen verfügbar macht.  Die Tablettstiftereignisse verfügen über Tunneling\/Bubbling\-Ereignispaare und treten immer im Anwendungsthread auf.  Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 In der folgenden Abbildung werden die Objektmodelle für die Klassen verglichen, die Tablettstiftereignisse auslösen.  Im WPF\-Objektmodell werden nur die Bubbling\-Ereignisse angezeigt, nicht die zugehörigen Tunneling\-Ereignisse.  
  
 ![Diagramm der Stylus&#45;Ereignisse in WPF im Vergleich zu Winforms.](../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink\_StylusEvents")  
  
## Stiftdaten  
 Alle drei Plattformen bieten Möglichkeiten zum Erfassen und Ändern der Daten von einem Tablettstift.  Auf der Windows Forms\- und der COM\-Plattform wird dies durch Erstellen von <xref:Microsoft.StylusInput.RealTimeStylus> erreicht. Ein Fenster oder Steuerelement wird angefügt und eine Klasse erstellt, die die <xref:Microsoft.StylusInput.IStylusSyncPlugin>\-Schnittstelle oder die <xref:Microsoft.StylusInput.IStylusAsyncPlugin>\-Schnittstelle implementiert.  Das benutzerdefinierte Plug\-In wird dann zur Plug\-In\-Auflistung von <xref:Microsoft.StylusInput.RealTimeStylus> hinzugefügt.  Weitere Informationen über dieses Objektmodell finden Sie unter [Architecture of the StylusInput APIs](http://msdn.microsoft.com/de-de/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 Auf der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plattform macht die <xref:System.Windows.UIElement>\-Klasse eine Auflistung von Plug\-Ins verfügbar, deren Entwurf <xref:Microsoft.StylusInput.RealTimeStylus> ähnelt.  Zum Erfassen von Stiftdaten erstellen Sie eine von <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> geerbte Klasse und fügen das Objekt dann zur <xref:System.Windows.UIElement.StylusPlugIns%2A>\-Auflistung von <xref:System.Windows.UIElement> hinzu.  Weitere Informationen zu dieser Interaktion finden Sie unter [Abfangen von Tablettstifteingaben](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 Auf allen Plattformen werden die Freihanddaten über Tablettstiftereignisse von einem Threadpool empfangen und an den Anwendungsthread gesendet.  Weitere Informationen zu Threading auf der COM\- und der Windows\-Plattform finden Sie unter [Threading Considerations for the StylusInput APIs](http://msdn.microsoft.com/de-de/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Weitere Informationen zu Threading in der Windows Presentation Software finden Sie unter [Das Threadmodell für Freihandeingaben](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 In der folgenden Abbildung werden die Objektmodelle für die Klassen verglichen, die Stiftereignisse im Threadpool für den Stift empfangen.  
  
 ![Diagramm des StylusPlugin&#45;Modells WPF im Vergleich zu WinForms.](../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink\_StylusPlugins")