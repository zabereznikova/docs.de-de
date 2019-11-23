---
title: Übersicht über Drag & Drop
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], implementing
- drag sources [WPF], drag-and-drop
- data transfer [WPF], drag-and-drop
- drag-and-drop [WPF], about
- drag-and-drop [WPF], events
- drop targets [WPF], drag-and-drop
ms.assetid: 1a5b27b0-0ac5-4cdf-86c0-86ac0271fa64
ms.openlocfilehash: 72dc443e5653b9871c3f67b003bd1af0536d5993
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291472"
---
# <a name="drag-and-drop-overview"></a>Übersicht über Drag & Drop
Dieses Thema enthält eine Übersicht zur Drag & Drop-Unterstützung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen. Drag & Drop bezeichnet im Allgemeinen eine Methode zur Datenübertragung, die die Verwendung einer Maus (oder eines anderen Zeigegeräts) zum Auswählen mindestens eines Objekts, das Ziehen dieses Objekts auf ein gewünschtes Ablageziels auf der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und dessen Ablegen beinhaltet.  

<a name="Drag_and_Drop_Support"></a>   
## <a name="drag-and-drop-support-in-wpf"></a>Drag & Drop-Unterstützung in WPF  
 An Drag & Drop-Vorgängen sind normalerweise zwei Seiten beteiligt: eine Ziehquelle, aus dem das gezogene Objekt stammt, und ein Ablageziel, das das abgelegte Objekt empfängt.  Bei der Ziehquelle und dem Ablageziel kann es sich um Benutzeroberflächenelemente in der gleichen Anwendung oder in verschiedenen Anwendungen handeln.  
  
 Die Art und Anzahl der Objekte, die mit Drag & Drop bearbeitet werden können, ist beliebig. Beispielsweise stellen Dateien, Ordner und ausgewählte Inhaltsbereiche gängige Objekte dar, die mithilfe von Drag & Drop-Vorgängen bearbeitet werden.  
  
 Die Aktionen, die im Einzelnen im Rahmen von Drag & Drop-Vorgängen ausgeführt werden, sind anwendungsspezifisch und werden oft durch den Kontext festgelegt.  Wenn Sie z. b. eine Auswahl von Dateien aus einem Ordner in einen anderen Ordner auf demselben Speichergerät ziehen, werden die Dateien standardmäßig verschoben, während Dateien aus einer Universal Naming Convention-Freigabe (UNC) in einen lokalen Ordner kopiert werden.  
  
 Die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zur Verfügung gestellten Drag & Drop-Möglichkeiten sind äußerst flexibel und anpassbar, um eine große Bandbreite von Drag & Drop-Szenarien zu unterstützen.  Drag-and-Drop unterstützt das Bearbeiten von Objekten innerhalb einer einzelnen Anwendung oder zwischen verschiedenen Anwendungen. Das ziehen und Ablegen zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen und anderen Windows-Anwendungen wird ebenfalls vollständig unterstützt.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können beliebige <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> an Drag &amp; Drop-Vorgängen beteiligt sein. Die für Drag &amp; Drop-Vorgänge erforderlichen Ereignisse und Methoden sind in der <xref:System.Windows.DragDrop>-Klasse definiert. Die Klassen <xref:System.Windows.UIElement> und <xref:System.Windows.ContentElement> enthalten Aliase für die angefügten <xref:System.Windows.DragDrop>-Ereignisse, sodass ein geerbtes <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> in der Liste der Klassenelemente als Basiselement aufgeführt wird. Die an diese Ereignisse angefügten Ereignishandler werden an das zugrundeliegende angefügte <xref:System.Windows.DragDrop>-Ereignis angefügt und empfangen die gleiche Instanz der Ereignisdaten. Weitere Informationen finden Sie beim <xref:System.Windows.UIElement.Drop?displayProperty=nameWithType>-Ereignis.  
  
> [!IMPORTANT]
> OLE-Drag & Drop funktioniert in der Zone „Internet“ nicht.  
  
<a name="Data_Transfer"></a>   
## <a name="data-transfer"></a>Datenübertragung  
 Drag & Drop bildet einen Teil des allgemeineren Bereichs der Datenübertragung. Zur Datenübertragung gehören Drag & Drop- ebenso wie Kopieren und Einfügen-Vorgänge. Ein Drag & Drop-Vorgang ist analog zu einem Kopieren und Einfügen- oder Ausschneiden und Einfügen-Vorgang, der zum Übertragen von Daten von einem Objekt oder einer Anwendung auf ein anderes bzw. eine andere mithilfe der Zwischenablage des Systems verwendet wird. Für beide Arten von Vorgängen sind diese Voraussetzungen erforderlich:  
  
- Ein Quellobjekt, das die Daten bereitstellt.  
  
- Eine Möglichkeit zum vorübergehenden Speichern der übertragenen Daten.  
  
- Ein Zielobjekt, das die Daten empfängt.  
  
 Bei einem Kopieren und Einfügen-Vorgang wird die Zwischenablage des Systems verwendet, um die übertragenen Daten vorübergehend zu speichern; bei einem Drag &amp; Drop-Vorgang wird ein <xref:System.Windows.DataObject> zum Speichern der Daten verwendet. Konzeptionell besteht ein Datenobjekt aus mindestens einem Paar eines <xref:System.Object>, das die eigentlichen Daten enthält, und einem entsprechenden Datenformatbezeichner.  
  
 Die Ziehquelle leitet einen Drag &amp; Drop-Vorgang durch Aufrufen der statischen <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType>-Methode und Übergeben der übertragenen Daten an sie ein. Die <xref:System.Windows.DragDrop.DoDragDrop%2A>-Methode umschließt die Daten ggf. automatisch in einem <xref:System.Windows.DataObject>. Um mehr Kontrolle über das Datenformat zu erhalten, können Sie die Daten vor der Übergabe an die <xref:System.Windows.DataObject>-Methode mit einem <xref:System.Windows.DragDrop.DoDragDrop%2A> umschließen. Das Ablageziel ist für die Extraktion der Daten aus dem <xref:System.Windows.DataObject> zuständig. Weitere Informationen zum Arbeiten mit Datenobjekten finden Sie unter [Daten und Datenobjekte](data-and-data-objects.md).  
  
 Die Quelle und das Ziel eines Drag & Drop-Vorgangs sind normalerweise Elemente der Benutzeroberfläche; die tatsächlich übertragenen Daten haben aber in der Regel keine visuelle Darstellung. Sie können Code erstellen, der eine visuelle Darstellung der gezogenen Daten bereitstellt, wie es etwa beim Ziehen von Dateien im Windows-Explorer geschieht. Standardmäßig wird dem Benutzer eine Rückmeldung gegeben, indem die Form des Cursors geändert wird, um die Auswirkung darzustellen, die der Drag & Drop-Vorgang auf die Daten hat, etwa ob die Daten verschoben oder kopiert werden.  
  
### <a name="drag-and-drop-effects"></a>Auswirkungen von Drag & Drop-Vorgängen  
 Drag & Drop-Vorgänge können verschiedene Auswirkungen auf die übertragenen Daten haben. Beispielsweise können Sie die Daten kopieren oder sie verschieben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert eine <xref:System.Windows.DragDropEffects> Enumeration, die Sie verwenden können, um die Auswirkung eines Drag & Drop-Vorgangs anzugeben. In der Ziehquelle können Sie die Auswirkungen, die von der Quelle zugelassen werden, in der Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> angeben. Im Ablageziel können Sie die Auswirkung, die von der Quelle beabsichtigt ist, in der Eigenschaft <xref:System.Windows.DragEventArgs.Effects%2A> der Klasse <xref:System.Windows.DragEventArgs> angeben. Wenn das Ablageziel seine beabsichtigte Auswirkung im <xref:System.Windows.DragDrop.DragOver>-Ereignis angibt, werden diese Informationen im <xref:System.Windows.DragDrop.GiveFeedback>-Ereignis an die Zielquelle zurück übermittelt. Die Ziehquelle verwendet diese Informationen, um dem Benutzer mitzuteilen, welche Auswirkung das Ablegen auf dem Ablageziel auf die Daten haben wird. Wenn die Daten abgelegt werden, gibt das Ablageziel die tatsächlichen Auswirkungen im <xref:System.Windows.DragDrop.Drop>-Ereignis an. Diese Informationen werden als Rückgabewert der Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> zurück an die Ziehquelle übergeben. Wenn das Ablageziel eine Auswirkung zurückgibt, die in der Liste der `allowedEffects` der Ziehquelle nicht aufgeführt ist, wird der Drag & Drop-Vorgang abgebrochen, ohne dass eine Übertragung von Daten stattfindet.  
  
 Es muss beachtet werden, dass in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.Windows.DragDropEffects>-Werte nur für die Kommunikation zwischen der Ziehquelle und dem Ablageziel über die Auswirkungen des Drag &amp; Drop-Vorgangs verwendet werden. Die tatsächliche Auswirkung des Drag & Drop-Vorgangs hängt von dem entsprechenden Code ab, den Sie für Ihre Anwendung schreiben.  
  
 Beispielsweise kann das Ablageziel angeben, dass die Auswirkung des Ablegens von Daten auf ihm die Verschiebung der Daten ist. Jedoch müssen die Daten zum Verschieben sowohl dem Zielelement hinzugefügt als auch aus dem Quellelement entfernt werden. Das Quellelement kann beispielsweise angeben, dass es das Verschieben der Daten erlaubt. Wenn Sie aber nicht den Code bereitstellen, um die Daten aus dem Quellelement zu entfernen, ergibt sich als Endergebnis, dass die Daten kopiert statt verschoben werden.  
  
<a name="Drag_and_Drop_Events"></a>   
## <a name="drag-and-drop-events"></a>Drag & Drop-Ereignisse  
 Drag & Drop-Vorgänge unterstützen ein ereignisgesteuertes Modell.  Sowohl die Ziehquelle als auch das Ablageziel verwenden einen Satz von Standardereignissen beim Verarbeiten von Drag & Drop-Vorgängen.  Die standardmäßigen Drag & Drop-Ereignisse sind in den folgenden Tabellen zusammengefasst. Dies sind angefügte Ereignisse der Klasse <xref:System.Windows.DragDrop>. Weitere Informationen zu angefügten Ereignissen finden Sie unter [Übersicht über angefügte Ereignisse](attached-events-overview.md).  
  
### <a name="drag-source-events"></a>Ereignisse der Ziehquelle  
  
|Ereignis|Zusammenfassung|  
|-----------|-------------|  
|<xref:System.Windows.DragDrop.GiveFeedback>|Dieses Ereignis tritt während eines Drag & Drop-Vorgangs fortlaufend ein und ermöglicht der Ziehquelle, dem Benutzer Rückmeldung zu geben. Diese Rückmeldung erfolgt üblicherweise durch Ändern der Form des Mauszeigers, um die vom Ablageziel zugelassenen Auswirkungen anzuzeigen.  Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.QueryContinueDrag>|Dieses Ereignis tritt ein, wenn während eines Drag & Drop-Vorgangs eine Änderung am Zustand der Tastatur- oder Maustasten eintritt, und ermöglicht dem Ablageziel, den Drag & Drop-Vorgang abhängig von den Tastenzuständen abzubrechen. Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.PreviewGiveFeedback>|Tunnelversion von <xref:System.Windows.DragDrop.GiveFeedback>.|  
|<xref:System.Windows.DragDrop.PreviewQueryContinueDrag>|Tunnelversion von <xref:System.Windows.DragDrop.QueryContinueDrag>.|  
  
### <a name="drop-target-events"></a>Ereignisse des Ablageziels  
  
|Ereignis|Zusammenfassung|  
|-----------|-------------|  
|<xref:System.Windows.DragDrop.DragEnter>|Dieses Ereignis tritt beim Ziehen eines Objekts in die Begrenzung des Ablageziels ein. Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.DragLeave>|Dieses Ereignis tritt beim Ziehen eines Objekts aus der Begrenzung des Ablageziels ein.  Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.DragOver>|Dieses Ereignis tritt fortlaufend auf, während ein Objekt innerhalb der Begrenzung des Ablageziels gezogen (bewegt) wird. Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.Drop>|Dieses Ereignis tritt ein, wenn ein Objekt auf dem Ablageziel abgelegt wird.  Dies ist ein Bubbling-Ereignis.|  
|<xref:System.Windows.DragDrop.PreviewDragEnter>|Tunnelversion von <xref:System.Windows.DragDrop.DragEnter>.|  
|<xref:System.Windows.DragDrop.PreviewDragLeave>|Tunnelversion von <xref:System.Windows.DragDrop.DragLeave>.|  
|<xref:System.Windows.DragDrop.PreviewDragOver>|Tunnelversion von <xref:System.Windows.DragDrop.DragOver>.|  
|<xref:System.Windows.DragDrop.PreviewDrop>|Tunnelversion von <xref:System.Windows.DragDrop.Drop>.|  
  
 Um Drag & Drop-Ereignisse für Instanzen eines Objekts zu verarbeiten, fügen Sie Handler für die in den vorhergehenden Tabellen aufgelisteten Ereignisse hinzu. Um Drag & Drop-Ereignisse auf der Klassenebene zu verarbeiten, überschreiben Sie die entsprechenden virtuellen On*Event- und On\*PreviewEvent-Methoden. Weitere Informationen finden Sie unter [Klassenbehandlung von Routingereignissen durch Steuerelement-Basisklassen](marking-routed-events-as-handled-and-class-handling.md#Class_Handling_of_Routed_Events).  
  
<a name="Implementing_Drag_And_Drop"></a>   
## <a name="implementing-drag-and-drop"></a>Implementierung von Drag & Drop  
 Ein Benutzerelement kann eine Ziehquelle, ein Ablageziel oder beides darstellen. Zum Implementieren der grundlegenden Drag & Drop-Funktionalität müssen Sie Code zum Einleiten des Drag & Drop-Vorgangs und zu Verarbeiten der abgelegten Daten erstellen. Sie können die Drag & Drop-Erfahrung durch Verarbeitung optionaler Drag & Drop-Ereignisse verbessern.  
  
 Zum Implementieren der grundlegenden Drag & Drop-Funktionalität müssen Sie die folgenden Schritte ausführen:  
  
- Ermitteln des Elements, das als Ziehquelle fungieren soll. Eine Ziehquelle kann ein <xref:System.Windows.UIElement> oder ein <xref:System.Windows.ContentElement> sein.  
  
- Einen Ereignishandler in der Ziehquelle erstellen, der den Drag & Drop-Vorgang einleitet. Das zu verarbeitende Ereignis ist normalerweise das <xref:System.Windows.UIElement.MouseMove>-Ereignis.  
  
- Im Ereignishandler der Ziehquelle die Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> aufrufen, um den Drag &amp; Drop-Vorgang einzuleiten. Geben Sie im <xref:System.Windows.DragDrop.DoDragDrop%2A>-Aufruf die Ziehquelle, die zu übertragenden Daten und die zulässigen Auswirkungen an.  
  
- Ermitteln des Elements das als Ablageziel dienen soll. Ein Ablageziel kann ein <xref:System.Windows.UIElement> oder ein <xref:System.Windows.ContentElement> sein.  
  
- Legen Sie auf dem Ablageziel die <xref:System.Windows.UIElement.AllowDrop%2A>-Eigenschaft auf `true` fest.  
  
- Erstellen Sie im Ablageziel einen <xref:System.Windows.DragDrop.Drop>-Ereignishandler, um die abgelegten Daten zu verarbeiten.  
  
- Extrahieren Sie im <xref:System.Windows.DragDrop.Drop>-Ereignishandler die Daten mithilfe der Methoden <xref:System.Windows.DragEventArgs> und <xref:System.Windows.DataObject.GetDataPresent%2A> aus den <xref:System.Windows.DataObject.GetData%2A>.  
  
- Verwenden Sie die Daten im <xref:System.Windows.DragDrop.Drop>-Ereignishandler, um den gewünschten Drag &amp; Drop-Vorgang auszuführen.  
  
 Sie können Ihre Drag &amp; Drop-Implementierung erweitern, indem Sie ein benutzerdefiniertes <xref:System.Windows.DataObject> erstellen und optionale Ereignisse der Ziehquelle und des Ablageziels verarbeiten, wie in den folgenden Aufgaben dargestellt:  
  
- Um benutzerdefinierte Daten oder mehrere Datenelemente zu übertragen, erstellen Sie ein <xref:System.Windows.DataObject>, das Sie an die <xref:System.Windows.DragDrop.DoDragDrop%2A>-Methode übergeben.  
  
- Um während eines Ziehvorgangs weitere Aktionen auszuführen, verarbeiten Sie die Ereignisse <xref:System.Windows.DragDrop.DragEnter>, <xref:System.Windows.DragDrop.DragOver> und <xref:System.Windows.DragDrop.DragLeave> des Ablageziels.  
  
- Um die Darstellung des Mauszeigers zu ändern, verarbeiten Sie das <xref:System.Windows.DragDrop.GiveFeedback>-Ereignis der Ziehquelle.  
  
- Um die Weise zu ändern, in der der Drag &amp; Drop-Vorgang abgebrochen wird, verarbeiten Sie das <xref:System.Windows.DragDrop.QueryContinueDrag>-Ereignis der Ziehquelle.  
  
<a name="Drag_And_Drop_Example"></a>   
## <a name="drag-and-drop-example"></a>Drag & Drop-Beispiel  
 In diesem Abschnitt wird die Implementierung von Drag &amp; Drop für ein <xref:System.Windows.Shapes.Ellipse>-Element beschrieben. Die <xref:System.Windows.Shapes.Ellipse> stellt sowohl eine Ziehquelle als auch ein Ablageziel dar. Die übertragenen Daten sind die Zeichenfolgendarstellung der <xref:System.Windows.Shapes.Shape.Fill%2A>-Eigenschaft der Ellipse. Der folgende XAML-Code zeigt das <xref:System.Windows.Shapes.Ellipse>-Element und die mit Drag &amp; Drop zusammenhängenden Ereignisse, die es verarbeitet. Eine ausführliche Anleitung zum Implementieren der Drag & Drop-Funktion finden Sie unter [Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement](walkthrough-enabling-drag-and-drop-on-a-user-control.md).  
  
 [!code-xaml[DragDropSnippets#EllipseXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#ellipsexaml)]  
  
### <a name="enabling-an-element-to-be-a-drag-source"></a>Aktivieren eines Elements als Ziehquelle  
 Ein Objekt, das eine Ziehquelle darstellt, ist für Folgendes zuständig:  
  
- Erkennen, wenn ein Ziehvorgang eintritt.  
  
- Einleiten des Drag & Drop-Vorgangs.  
  
- Identifizieren der zu übertragenden Daten.  
  
- Angeben der zulässigen Auswirkungen, die der Drag & Drop-Vorgang auf die übertragenen Daten haben darf.  
  
 Die Ziehquelle kann darüber hinaus Rückmeldung an den Benutzer hinsichtlich der zulässigen Aktionen (Verschieben, Kopieren, keine) geben und den Drag & Drop-Vorgang auf der Grundlage weiterer Benutzereingaben, wie etwa Drücken der ESC-Taste während des Ziehens, abbrechen.  
  
 Zu Bestimmen, wann ein Ziehvorgang eintritt, liegt in der Zuständigkeit Ihrer Anwendung, die anschließend den Drag &amp; Drop-Vorgang durch Aufrufen der Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> einleiten muss. Dies ist normalerweise der Fall, wenn ein <xref:System.Windows.UIElement.MouseMove>-Ereignis über dem zu ziehenden Element eintritt, während eine Maustaste gedrückt wird. Im folgenden Beispiel ist zu sehen, wie ein Drag &amp; Drop-Vorgang vom <xref:System.Windows.UIElement.MouseMove>-Ereignishandler eines <xref:System.Windows.Shapes.Ellipse>-Elements eingeleitet wird, um es zu einer Ziehquelle zu machen. Die übertragenen Daten sind die Zeichenfolgendarstellung der <xref:System.Windows.Shapes.Shape.Fill%2A>-Eigenschaft der Ellipse.  
  
 [!code-csharp[DragDropSnippets#DoDragDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dodragdrop)]
 [!code-vb[DragDropSnippets#DoDragDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dodragdrop)]  
  
 Rufen Sie im Innern des <xref:System.Windows.UIElement.MouseMove>-Ereignishandlers die Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> auf, um den Drag &amp; Drop-Vorgang einzuleiten. Die Methode <xref:System.Windows.DragDrop.DoDragDrop%2A> akzeptiert drei Parameter:  
  
- `dragSource` – ein Verweis auf das Abhängigkeits Objekt, das die Quelle der übertragenen Daten ist. Dies ist in der Regel die Quelle des <xref:System.Windows.UIElement.MouseMove> Ereignisses.  
  
- `data`-ein Objekt, das die übertragenen Daten enthält, die in einem <xref:System.Windows.DataObject>umschließt.  
  
- `allowedEffects`-einer der <xref:System.Windows.DragDropEffects> Enumerationswerte, der die zulässigen Auswirkungen des Drag & Drop-Vorgangs angibt.  
  
 Im Parameter `data` können beliebige serialisierbare Objekte übergeben werden. Wenn die Daten noch nicht von einem <xref:System.Windows.DataObject> umschlossen sind, werden sie automatisch von einem neuen <xref:System.Windows.DataObject> umschlossen. Zum Übergeben mehrerer Datenelemente müssen Sie das <xref:System.Windows.DataObject> selbst erstellen und es an die <xref:System.Windows.DragDrop.DoDragDrop%2A>-Methode übergeben. Weitere Informationen finden Sie unter [Daten und Datenobjekte](data-and-data-objects.md).  
  
 Der `allowedEffects`-Parameter wird verwendet, um anzugeben, welche Aktionen die Ziehquelle dem Ablageziel mit den übertragenen Daten erlaubt. Die üblichen Werte für eine Ziehquelle sind <xref:System.Windows.DragDropEffects.Copy>, <xref:System.Windows.DragDropEffects.Move> und <xref:System.Windows.DragDropEffects.All>.  
  
> [!NOTE]
> Das Ablageziel kann außerdem angeben, welche Auswirkungen es als Reaktion auf die Ablage der Daten beabsichtigt. Wenn das Ablageziel den Typ der abzulegenden Daten beispielsweise nicht erkennt, kann es die Daten zurückweisen, indem es die zulässigen Auswirkungen auf <xref:System.Windows.DragDropEffects.None> festlegt. Dies erfolgt normalerweise im <xref:System.Windows.DragDrop.DragOver>-Ereignishandler des Ablageziels.  
  
 Ziehquellen können optional die Ereignisse <xref:System.Windows.DragDrop.GiveFeedback> und <xref:System.Windows.DragDrop.QueryContinueDrag> verarbeiten. Diese Ereignisse weisen Standardhandler auf, die verwendet werden, sofern ein Ereignis nicht als behandelt gekennzeichnet wird. Normalerweise werden diese Ereignisse ignoriert, es sei denn, es besteht eine spezifische Notwendigkeit, ihr Standardverhalten zu ändern.  
  
 Das <xref:System.Windows.DragDrop.GiveFeedback>-Ereignis wird fortlaufend ausgelöst, während die Ziehquelle gezogen wird. Der Standardhandler für dieses Ereignis überprüft, ob die Ziehquelle sich über einem gültigen Ablageziel befindet. Ist das der Fall, überprüft er die zulässigen Auswirkungen des Ablageziels. Dann gibt er dem Endbenutzer Rückmeldung hinsichtlich der zulässigen Ablageauswirkungen. Dies erfolgt normalerweise durch Ändern des Mauscursors in einen Nicht ablegen-, Kopier- oder Verschiebecursor. Sie sollten dieses Ereignis nur verarbeiten, wenn Sie benutzerdefinierte Cursor verwenden müssen, um dem Benutzer Rückmeldung zu geben. Wenn Sie dieses Ereignis behandeln, markieren Sie es als behandelt, damit der Standardhandler Ihren Handler nicht überschreibt.  
  
 Das <xref:System.Windows.DragDrop.QueryContinueDrag>-Ereignis wird fortlaufend ausgelöst, während die Ziehquelle gezogen wird. Sie können dieses Ereignis verarbeiten, um zu bestimmen, welche Aktion den Drag & Drop-Vorgang beendet, basierend auf dem Zustand der Tasten ESC, UMSCHALT, STRG und ALT sowie dem Zustand der Maustasten. Der Standardhandler für dieses Ereignis bricht den Drag & Drop-Vorgang ab, wenn die ESC-Taste gedrückt wird, und legt die Daten ab, wenn die Maustaste freigegeben wird.  
  
> [!CAUTION]
> Diese Ereignisse werden während des Drag & Drop-Vorgangs fortlaufend ausgelöst. Daher sollten ressourcenintensive Tasks in den Ereignishandlern vermieden werden.  Verwenden Sie z. B. einen zwischengespeicherten Cursor, statt bei jeder Auslösung des <xref:System.Windows.DragDrop.GiveFeedback>-Ereignisses einen neuen Cursor zu erstellen.  
  
### <a name="enabling-an-element-to-be-a-drop-target"></a>Aktivieren eines Elements als Ablageziel  
 Ein Objekt, das ein Ablageziel darstellt, ist für Folgendes zuständig:  
  
- Angeben, dass es sich um ein gültiges Ablageziel handelt.  
  
- Reagieren auf die Ziehquelle, wenn sie über das Ziel gezogen wird.  
  
- Überprüfen, ob die übertragenen Daten in einem empfangbaren Format vorliegen.  
  
- Verarbeiten der abgelegten Daten.  
  
 Um anzugeben, dass ein Element ein Ablageziel ist, legen Sie seine <xref:System.Windows.UIElement.AllowDrop%2A>-Eigenschaft auf `true` fest. Dadurch werden die Ablagezielereignisse für das Element ausgelöst, sodass Sie sie verarbeiten können. Während eines Drag & Drop-Vorgang tritt die folgenden Reihenfolge der Ereignisse beim Ablageziel auf:  
  
1. <xref:System.Windows.DragDrop.DragEnter>  
  
2. <xref:System.Windows.DragDrop.DragOver>  
  
3. <xref:System.Windows.DragDrop.DragLeave> oder <xref:System.Windows.DragDrop.Drop>  
  
 Das <xref:System.Windows.DragDrop.DragEnter>-Ereignis tritt ein, wenn die Daten in den Begrenzung des Ablageziels gezogen werden. Normalerweise verarbeiten Sie dieses Ereignis, um eine Vorschau der Auswirkungen des Drag & Drop-Vorgangs bereitzustellen, wenn das in Ihrer Anwendung sinnvoll ist. Legen Sie nicht die <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType>-Eigenschaft im Ereignis <xref:System.Windows.DragDrop.DragEnter> fest, da sie im <xref:System.Windows.DragDrop.DragOver>-Ereignis überschrieben wird.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.DragDrop.DragEnter>-Ereignishandler für ein <xref:System.Windows.Shapes.Ellipse>-Element. Dieser Code bewirkt eine Vorschau der Auswirkungen des Drag &amp; Drop-Vorgangs durch Speichern des aktuellen <xref:System.Windows.Shapes.Shape.Fill%2A>-Pinsels. Anschließend wird die Methode <xref:System.Windows.DataObject.GetDataPresent%2A> verwendet, um zu überprüfen, ob das <xref:System.Windows.DataObject>-Objekt, das über die Ellipse gezogen wird, Zeichenfolgendaten enthält, die in einen <xref:System.Windows.Media.Brush> konvertiert werden können. Ist das der Fall, werden die Daten mithilfe der <xref:System.Windows.DataObject.GetData%2A>-Methode extrahiert. Anschließend werden sie in einen <xref:System.Windows.Media.Brush> konvertiert und auf die Ellipse angewendet. Die Änderung wird im <xref:System.Windows.DragDrop.DragLeave>-Ereignishandler rückgängig gemacht. Wenn die Daten nicht in einen <xref:System.Windows.Media.Brush> konvertiert werden können, wird keine Aktion ausgeführt.  
  
 [!code-csharp[DragDropSnippets#DragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragenter)]
 [!code-vb[DragDropSnippets#DragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragenter)]  
  
 Das <xref:System.Windows.DragDrop.DragOver>-Ereignis wird kontinuierlich ausgelöst, während die Daten über das Ablageziel gezogen werden. Dieses Ereignis ist mit dem <xref:System.Windows.DragDrop.GiveFeedback>-Ereignis der Ziehquelle gekoppelt. Im <xref:System.Windows.DragDrop.DragOver>-Ereignishandler verwenden Sie normalerweise die Methoden <xref:System.Windows.DataObject.GetDataPresent%2A> und <xref:System.Windows.DataObject.GetData%2A>, um zu prüfen, ob die übertragenen Daten in einem Format vorliegen, das vom Ablageziel verarbeitet werden kann. Darüber hinaus können Sie prüfen, ob Modifizierertasten gedrückt sind, was normalerweise anzeigt, ob der Benutzer eine Verschiebe- oder eine Kopieraktion beabsichtigt. Nachdem diese Prüfungen vorgenommen wurden, legen Sie die <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType>-Eigenschaft fest, um die Ziehquelle zu benachrichtigen, welche Auswirkungen das Ablegen der Daten hat. Die Ziehquelle empfängt diese Informationen in den <xref:System.Windows.DragDrop.GiveFeedback>-Ereignisargumenten und kann einen geeigneten Cursor festlegen, um dem Benutzer Rückmeldung zu geben.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.DragDrop.DragOver>-Ereignishandler für ein <xref:System.Windows.Shapes.Ellipse>-Element. Dieser Code überprüft, ob das über die Ellipse gezogene <xref:System.Windows.DataObject> Zeichenfolgendaten enthält, die in einen <xref:System.Windows.Media.Brush> konvertiert werden können. In diesem Fall legt er die <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType>-Eigenschaft als <xref:System.Windows.DragDropEffects.Copy> fest. Dies zeigt der Ziehquelle an, dass die Daten zur Ellipse kopiert werden können. Wenn die Daten nicht in einen <xref:System.Windows.Media.Brush> konvertiert werden können, wird die Eigenschaft <xref:System.Windows.DragEventArgs.Effects%2A?displayProperty=nameWithType> auf <xref:System.Windows.DragDropEffects.None> festgelegt. Dieses zeigt der Datenquelle an, dass die Ellipse kein gültiges Ablageziel für die Daten darstellt.  
  
 [!code-csharp[DragDropSnippets#DragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragover)]
 [!code-vb[DragDropSnippets#DragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragover)]  
  
 Das <xref:System.Windows.DragDrop.DragLeave>-Ereignis tritt ein, wenn die Daten aus der Begrenzung des Ziels heraus gezogen werden, ohne abgelegt worden zu sein. Sie behandeln dieses Ereignis, um alles rückgängig zu machen, was Sie im <xref:System.Windows.DragDrop.DragEnter>-Ereignishandler ausgeführt haben.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.DragDrop.DragLeave>-Ereignishandler für ein <xref:System.Windows.Shapes.Ellipse>-Element. Dieser Code macht die im <xref:System.Windows.DragDrop.DragEnter>-Ereignishandler ausgeführte Vorschau rückgängig, indem er den gespeicherten <xref:System.Windows.Media.Brush> auf die Ellipse anwendet.  
  
 [!code-csharp[DragDropSnippets#DragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#dragleave)]
 [!code-vb[DragDropSnippets#DragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#dragleave)]  
  
 Das <xref:System.Windows.DragDrop.Drop>-Ereignis tritt ein, wenn die Daten über dem Ablageziel abgelegt werden; standardmäßig geschieht dies beim Freigeben der Maustaste. Im <xref:System.Windows.DragDrop.Drop>-Ereignishandler verwenden Sie die Methode <xref:System.Windows.DataObject.GetData%2A>, um die übertragenen Daten aus dem <xref:System.Windows.DataObject> zu extrahieren und jede von Ihrer Anwendung benötigte Datenverarbeitung auszuführen. Das <xref:System.Windows.DragDrop.Drop>-Ereignis beendet den Drag &amp; Drop-Vorgang.  
  
 Das folgende Beispiel zeigt den <xref:System.Windows.DragDrop.Drop>-Ereignishandler für ein <xref:System.Windows.Shapes.Ellipse>-Element. Dieser Code wendet die Auswirkungen des Drag &amp; Drop-Vorgan an und ähnelt dem Code im <xref:System.Windows.DragDrop.DragEnter>-Ereignishandler. Er überprüft, ob das <xref:System.Windows.DataObject>, das über die Ellipse gezogen wird, Zeichenfolgendaten enthält, die in einen <xref:System.Windows.Media.Brush> konvertiert werden können. In diesem Fall wird der <xref:System.Windows.Media.Brush> auf die Ellipse angewendet. Wenn die Daten nicht in einen <xref:System.Windows.Media.Brush> konvertiert werden können, wird keine Aktion ausgeführt.  
  
 [!code-csharp[DragDropSnippets#Drop](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#drop)]
 [!code-vb[DragDropSnippets#Drop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#drop)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Clipboard>
- [Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement](walkthrough-enabling-drag-and-drop-on-a-user-control.md)
- [Themen zur Vorgehensweise zu einem Expander](drag-and-drop-how-to-topics.md)
- [Drag & Drop](drag-and-drop.md)
