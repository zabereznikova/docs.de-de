---
title: 'Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF'
ms.date: 03/30/2017
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
ms.openlocfilehash: 68003943041fe0ba405eff1236c43a8e7e9c2b71
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356831"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Das Freihandobjektmodell: Windows Forms und COM im Vergleich zu WPF

Es gibt im Wesentlichen drei Plattformen, die Freihandeingaben zu unterstützen: die Tablet PC, Windows Forms-Plattform, die COM-Tablet-PC-Plattform und die Windows Presentation Foundation (WPF)-Plattform.  Die Freigabe für Windows Forms und COM-Plattformen ein ähnliches Objektmodell, aber das Objekt zu, für modellieren die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Plattform unterscheidet sich deutlich.  Dieses Thema beschreibt die Unterschiede auf hoher Ebene, damit Entwickler, die mit einem Objektmodell gearbeitet haben, können die anderen besser verstehen.  
  
## <a name="enabling-ink-in-an-application"></a>Aktivieren von Freihandeingaben in einer Anwendung  
 Alle drei Plattformen enthalten, Objekten und Steuerelementen, mit die eine Anwendung, um Eingaben von einem Stift erhalten können.  Im Lieferumfang der Windows Forms und COM-Plattform [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) und [ Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) Klassen.  [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) und [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) sind Steuerelemente, die Sie hinzufügen können, um eine Anwendung zum Erfassen von Freihandeingaben.  Die [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) und [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) an ein vorhandenes Fenster an Freihandeingaben zu ermöglichen, Windows und benutzerdefinierte Steuerelemente angefügt werden können.  
  
 Die WPF-Plattform umfasst die <xref:System.Windows.Controls.InkCanvas> Steuerelement.  Hinzufügbaren ein <xref:System.Windows.Controls.InkCanvas> für Ihre Anwendung und sofort Freihandeingaben erfassen. Mit der <xref:System.Windows.Controls.InkCanvas>, der Benutzer kopieren, wählen und Freihandeingaben die Größe ändern kann.  Sie können andere Steuerelemente zum Hinzufügen der <xref:System.Windows.Controls.InkCanvas>, und der Benutzer kann von Hand schreiben über die Steuerelemente zu.  Sie können ein Freihandeingaben benutzerdefiniertes Steuerelement erstellen, durch das Hinzufügen einer <xref:System.Windows.Controls.InkPresenter> und die Tablettstiftpunkte erfassen.  
  
 Die folgende Tabelle enthält, wo Sie weitere Informationen zum Aktivieren von Freihandeingaben in einer Anwendung:  
  
|Zu diesem Zweck...|Auf der WPF-Plattform...|Auf den Windows Forms/COM-Plattformen...|  
|-----------------|--------------------------|------------------------------------------|  
|Hinzufügen eines Steuerelements Freihandeingaben zu einer Anwendung|Finden Sie unter [erste Schritte mit Freihandeingaben](getting-started-with-ink.md).|Finden Sie unter [automatisch Ansprüche bilden, Beispiel](/windows/desktop/tablet/auto-claims-form-sample)|  
|Aktivieren von Freihandeingaben auf einem benutzerdefinierten Steuerelement|Finden Sie unter [erstellen einen in Freihand gezeichneten Steuerelements Eingabe](creating-an-ink-input-control.md).|Finden Sie unter [Ink-Beispiel für die Zwischenablage](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Freihanddaten  
 Auf der Windows Forms und COM-Plattform [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), und [ Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) jedes machen eine [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) Objekt. Die [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) Objekt enthält die Daten für eine oder mehrere [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) Objekte und stellt allgemeine Methoden und Eigenschaften zum Verwalten und ändern die Striche.  Die [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) -Objekt verwaltet die Lebensdauer der Striche enthält, die [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) -Objekt erstellt und löscht die Striche, die dieser besitzt.  Jede [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) verfügt über einen Bezeichner, der eindeutig innerhalb des übergeordneten [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) Objekt.  
  
 Auf der WPF-Plattform die <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> Klasse besitzt und verwaltet seine eigene Gültigkeitsdauer. Eine Gruppe von <xref:System.Windows.Ink.Stroke> Objekte können zusammen gesammelt werden, einem <xref:System.Windows.Ink.StrokeCollection>, drücken Sie die Methoden für allgemeine Freihandeingaben datenverwaltungsvorgängen bereitstellt, z.B. testen, bereinigen, Transformieren und Serialisieren von Freihandeingaben. Ein <xref:System.Windows.Ink.Stroke> kann zu 0 (null), ein oder mehrere gehören <xref:System.Windows.Ink.StrokeCollection> Objekte auf einer Räumen Sie Zeit.  Anstatt eine [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) -Objekt, das <xref:System.Windows.Controls.InkCanvas> und <xref:System.Windows.Controls.InkPresenter> enthalten eine <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 Die folgenden zwei Abbildungen werden die Objektmodelle von Freihandeingaben Daten verglichen.  Auf der Windows Forms und COM-Plattform die [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) Objekt schränkt die Lebensdauer des der [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) Objekte und die Stift-Pakete, die zu den einzelnen Strichen gehören.  Mindestens zwei Striche können verweisen, dasselbe [Microsoft.Ink.DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) Objekt, wie in der folgenden Abbildung gezeigt.  
  
 ![Diagramm des Freihandeingabe-Objektmodells für COM-&#47;Winforms. ](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die jeweils <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> ist ein Objekt von common Language Runtime, die vorhanden ist, solange ein einen Verweis darauf verfügt.  Jede <xref:System.Windows.Ink.Stroke> Verweise ein <xref:System.Windows.Input.StylusPointCollection> und <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> -Objekt, das common Language Runtime-Objekte auch sind.  
  
 ![Diagramm des Freihandeingabe-Objektmodells für WPF. ](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Die folgende Tabelle vergleicht, wie einige häufige Aufgaben für die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plattform und die Plattformen Windows Forms und COM.  
  
|Aufgabe|Windows Presentation Foundation|Windows Forms und COM|  
|----------|-------------------------------------|---------------------------|  
|Speichern von Freihandeingaben|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|Laden von Freihandeingaben|Erstellen Sie eine <xref:System.Windows.Ink.StrokeCollection> mit der <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> Konstruktor.|[Microsoft.Ink.Ink.Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|Treffertests|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|Kopieren von Freihandeingaben|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|Einfügen von Freihandeingaben|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|Zugriff auf benutzerdefinierte Eigenschaften auf eine Auflistung von Strichen|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (die Eigenschaften werden intern gespeichert und auf das über <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, und <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Verwendung [Microsoft.Ink.Ink.ExtendedProperties](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>Freigeben von Freihandeingaben auf verschiedenen Plattformen  
 Obwohl die Plattformen unterschiedliche Objektmodelle für die Freihandeingaben Daten verfügen, ist die Freigabe von Daten zwischen den Plattformen sehr einfach. In den folgenden Beispielen Freihandeingaben aus einer Windows Forms-Anwendung gespeichert und in einer Windows Presentation Foundation-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 In den folgenden Beispielen Freihandeingaben aus einem Windows Presentation Foundation-Anwendung gespeichert und in einer Windows Forms-Anwendung geladen.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Ereignisse, die vom Tablettstift  

 Die [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), und [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) empfangen von Ereignissen auf dem Windows Forms und COM-Plattformen bei der der Benutzer Eingaben pen-Daten. Die [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) oder [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) für ein Fenster oder ein Steuerelement angefügt ist, und können die Ereignisse abonnieren, durch die Tabletteingabedaten ausgelöst. Der Thread, der auf dem diese Ereignisse auftreten, hängt davon ab, ob die Ereignisse, mit einem Stift, Maus ausgelöst werden, oder programmgesteuert. Weitere Informationen zu threading in Bezug auf diese Ereignisse finden Sie unter [Allgemeines Threading](/windows/desktop/tablet/general-threading-considerations) und [Threads auf das Auslösen eines Ereignisses kann](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 Auf der Windows Presentation Foundation-Plattform die <xref:System.Windows.UIElement> -Klasse verfügt über Ereignisse für Stifteingaben. Dies bedeutet, dass jedes Steuerelement den vollständigen Satz von Stift-Ereignisse verfügbar macht.  Die Stiftereignisse besitzen tunneling/bubbling-Ereignis-Paare und immer auf dem Thread der Anwendung erfolgen.  Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 Das folgende Diagramm zeigt vergleicht die Objektmodelle für die Klassen, die Stiftereignisse auslösen. Das Windows Presentation Foundation-Objektmodell zeigt nur die bubbling-Ereignisse, nicht die Tunneling-Ereignis-Entsprechungen.  
  
 ![Diagramm der Stylus-Ereignisse in WPF im Vergleich zu Winforms. ](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Stift-Daten  
 Alle drei Plattformen bieten Ihnen Methoden zum Abfangen und bearbeiten die Daten, die von einem Tablettstift eingeht.  Auf dem Windows Forms und COM-Plattform, dies erfolgt durch Erstellen einer [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)), Anfügen eines Fensters oder Steuerelements, und erstellen Sie eine Klasse, implementiert die [ Microsoft.StylusInput.IStylusSyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) oder [Microsoft.StylusInput.IStylusAsyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) Schnittstelle. Das benutzerdefinierte plug-in wird dann hinzugefügt, auf die Plug-in-Auflistung von der [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)). Weitere Informationen zu diesem Objektmodell, finden Sie unter [Architektur der StylusInput APIs](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 Auf der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plattform, die <xref:System.Windows.UIElement> Klasse stellt eine Auflistung von-Plug-ins, Entwurf, ähnelt die [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)).  Zum Abfangen von Stift-Daten, erstellen Sie eine Klasse, die von erbt <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> und fügen Sie das Objekt, das die <xref:System.Windows.UIElement.StylusPlugIns%2A> Auflistung von der <xref:System.Windows.UIElement>. Weitere Informationen zu dieser Aktivität, finden Sie unter [Abfangen der Eingabe des Tablettstifts](intercepting-input-from-the-stylus.md).  
  
 Auf allen Plattformen ein Threadpools die Freihanddaten über Stift-Ereignisse empfängt und sendet sie an den Anwendungsthread.  Weitere Informationen zu den für die Windows-Plattformen, COM-threading, finden Sie unter [Threading Überlegungen für die StylusInput APIs](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Weitere Informationen zu den in der Windows Presentation Software threading, finden Sie unter [das Threadmodell für Freihandeingaben](the-ink-threading-model.md).  
  
 Die folgende Abbildung vergleicht die Objektmodelle für die Klassen, die Daten der Stift auf Stiftthreadpool empfangen.  
  
 ![Diagramm des StylusPlugIn-Modells WPF im Vergleich Winforms. ](./media/ink-stylusplugins.png "Ink_StylusPlugins")
