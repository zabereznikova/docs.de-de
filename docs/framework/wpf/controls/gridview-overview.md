---
title: Übersicht über GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 6da556296679de1161f609a7731c6fbf14e94730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966473"
---
# <a name="gridview-overview"></a>Übersicht über GridView
<xref:System.Windows.Controls.GridView>der Ansichtsmodus ist einer der Ansichtsmodi <xref:System.Windows.Controls.ListView> für ein Steuerelement. Mithilfe <xref:System.Windows.Controls.GridView> der-Klasse und der unterstützenden Klassen können Sie und Ihre Benutzer Element Auflistungen in einer Tabelle anzeigen, in der normalerweise Schaltflächen als interaktive Spaltenheader verwendet werden. In diesem Thema wird <xref:System.Windows.Controls.GridView> die-Klasse vorgestellt und deren Verwendung beschrieben.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Was ist eine GridView-Ansicht?  
 Im <xref:System.Windows.Controls.GridView> Ansichtsmodus wird eine Liste von Datenelementen angezeigt, indem Datenfelder an Spalten gebunden werden und ein Spaltenheader zum Identifizieren des Felds angezeigt wird. Der Standard <xref:System.Windows.Controls.GridView> Stil implementiert Schaltflächen als Spaltenheader. Mithilfe von Schaltflächen für Spaltenkopfzeilen können Sie wichtige Funktionen für die Benutzerinteraktion implementieren. Beispielsweise können Benutzer auf die Spaltenüberschrift klicken, <xref:System.Windows.Controls.GridView> um die Daten nach dem Inhalt einer bestimmten Spalte zu sortieren.  
  
> [!NOTE]
> Die Schaltflächen- <xref:System.Windows.Controls.GridView> Steuerelemente, die für Spaltenheader <xref:System.Windows.Controls.Primitives.ButtonBase>verwendet, werden von abgeleitet.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView> Inhaltsansicht.  
    
 ![Screenshot, der die GridView-Ansicht von ListView-Inhalt anzeigt.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>Spalten werden durch <xref:System.Windows.Controls.GridViewColumn> -Objekte dargestellt, die automatisch an ihren Inhalt anpassen können. Optional können Sie einen <xref:System.Windows.Controls.GridViewColumn> explizit auf eine bestimmte Breite festlegen. Sie können die Spaltenbreite mithilfe der Ziehelemente zwischen den Spaltenheadern anpassen. Sie können Spalten auch dynamisch hinzufügen, entfernen, ersetzen und neu anordnen, da diese Funktionalität in <xref:System.Windows.Controls.GridView>integriert ist. Die angezeigten <xref:System.Windows.Controls.GridView> Daten können jedoch nicht direkt aktualisiert werden.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.GridView> definiert wird, das Mitarbeiterdaten anzeigt. In diesem Beispiel <xref:System.Windows.Controls.ListView> definiert das `EmployeeInfoDataSource` als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Die Eigenschafts Definitionen <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> von <xref:System.Windows.Controls.GridViewColumn> Binden von `EmployeeInfoDataSource` Inhalten an Datenkategorien.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die nachstehende Abbildung zeigt die Tabelle, die mit dem vorherigen Beispiel erstellt wurde. Das GridView-Steuerelement zeigt Daten aus einem ItemsSource-Objekt an:
    
 ![Screenshot, der eine ListView mit GridView-Ausgabe zeigt.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>GridView-Layout und Stil  
 Die Spalten Zellen und der Spaltenheader eines <xref:System.Windows.Controls.GridViewColumn> haben dieselbe Breite. Standardmäßig ist jede Spalte so breit wie ihr Inhalt. Optional können Sie für eine Spalte auch eine feste Breite angeben.  
  
 Zusammengehörige Dateninhalte werden in horizontalen Zeilen angezeigt. Beispielsweise werden in der vorstehenden Abbildung Vorname, Nachname und ID eines Angestellten als ein Satz angezeigt, da sie sich in einer horizontalen Zeile befinden.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definieren und Formatieren von Spalten in einer GridView-Ansicht  
 Wenn Sie das Datenfeld definieren, das in <xref:System.Windows.Controls.GridViewColumn>einem angezeigt werden <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>soll, verwenden <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> Sie die Eigenschaften, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>oder. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft hat Vorrang vor den Vorlagen Eigenschaften.  
  
 Um die Ausrichtung des Inhalts in einer Spalte einer <xref:System.Windows.Controls.GridView>anzugeben, definieren Sie eine. <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Verwenden Sie die- <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> Eigenschaft <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> und die <xref:System.Windows.Controls.ListView> -Eigenschaft nicht für Inhalte, die <xref:System.Windows.Controls.GridView>mit einem angezeigt werden.  
  
 Um Vorlagen-und Stileigenschaften für Spaltenheader anzugeben, verwenden <xref:System.Windows.Controls.GridView>Sie <xref:System.Windows.Controls.GridViewColumn>die Klassen <xref:System.Windows.Controls.GridViewColumnHeader> , und. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Hinzufügen von visuellen Elementen zu einer GridView-Ansicht  
 Verwenden Sie Vorlagen oder Stile, um <xref:System.Windows.Controls.CheckBox> visuelle <xref:System.Windows.Controls.Button> Elemente, wie z <xref:System.Windows.Controls.GridView> . b.-und-Steuerelemente, zu einem Anzeigemodus hinzuzufügen.  
  
 Wenn Sie ein visuelles Element explizit als Datenelement definieren, kann es nur einmal in einem <xref:System.Windows.Controls.GridView>vorkommen. Diese Einschränkung besteht, weil ein Element nur ein übergeordnetes Element haben und deshalb auch nur ein Mal in der visuellen Struktur angezeigt werden kann.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Formatieren von Zeilen in einer GridView-Ansicht  
 Verwenden Sie <xref:System.Windows.Controls.GridViewRowPresenter> die <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Klassen und, um die Zeilen eines zu formatieren und <xref:System.Windows.Controls.GridView>anzuzeigen. Ein Beispiel für das Formatieren von Zeilen in einem <xref:System.Windows.Controls.GridView> Ansichtsmodus finden Sie unter Formatieren [einer Zeile in einem ListView-Steuer Punkt, der eine GridView implementiert](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um Ausrichtungs Probleme zwischen Spaltenüberschriften und Zellen zu vermeiden, legen Sie keine Eigenschaft fest, oder geben Sie eine Vorlage an, die sich <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>auf die Breite eines Elements in einem auswirkt. Legen Sie beispielsweise die-Eigenschaft <xref:System.Windows.FrameworkElement.Margin%2A> nicht fest, oder <xref:System.Windows.Controls.ControlTemplate> geben Sie einen <xref:System.Windows.Controls.CheckBox> an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> , der ein-Element einem <xref:System.Windows.Controls.ListView> hinzufügt, das in einem-Steuerelement definiert ist. Geben Sie stattdessen die Eigenschaften und Vorlagen, die die Spaltenbreite betreffen, direkt auf Klassen <xref:System.Windows.Controls.GridView> an, die einen Ansichtsmodus definieren.  
  
 Wenn Sie z. b. <xref:System.Windows.Controls.CheckBox> der Zeilen im <xref:System.Windows.Controls.GridView> Ansichtsmodus einen hinzufügen <xref:System.Windows.Controls.CheckBox> möchten, <xref:System.Windows.DataTemplate>fügen Sie den zu einem <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> hinzu, und <xref:System.Windows.DataTemplate>legen Sie dann die-Eigenschaft auf fest.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Benutzerinteraktionen mit einer GridView-Ansicht  
 Wenn Sie <xref:System.Windows.Controls.GridView> in Ihrer Anwendung verwenden, können Benutzer mit interagieren und die Formatierung <xref:System.Windows.Controls.GridView>von ändern. Benutzer können z.B. Spalten neu anordnen, vergrößern und verkleinern, Elemente in einer Tabelle auswählen und durch Tabelleninhalte scrollen. Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader-Schaltfläche klickt. Der Ereignishandler kann Vorgänge wie das Sortieren der Daten ausführen, die in der <xref:System.Windows.Controls.GridView> entsprechend dem Inhalt einer Spalte angezeigt werden.  
  
 In der folgenden Liste werden die Funktionen der Verwendung <xref:System.Windows.Controls.GridView> von für die Benutzerinteraktion ausführlicher erläutert:  
  
- **Neuanordnen von Spalten mithilfe der Drag & Drop-Methode**  
  
     Benutzer können Spalten in einer <xref:System.Windows.Controls.GridView> neu anordnen, indem Sie die linke Maustaste gedrückt halten, während Sie sich über einem Spaltenheader befindet, und dann diese Spalte an eine neue Position ziehen. Während der Benutzer den Spaltenheader zieht, wird eine schwebende Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die anzeigt, wo die Spalte eingefügt wird.  
  
     Wenn Sie den Standardstil für die unverankerte Version eines Headers ändern möchten, geben Sie <xref:System.Windows.Controls.ControlTemplate> einen für <xref:System.Windows.Controls.GridViewColumnHeader> einen Typ an, der ausgelöst <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> wird, wenn die <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>-Eigenschaft auf festgelegt ist. Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView-Spaltenheader](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Anpassen einer Spalte an ihren Inhalt**  
  
     Benutzer können durch einen Doppelklick auf die Ziehpunkte rechts neben Spaltenheadern Spalten an ihren Inhalt anpassen.  
  
    > [!NOTE]
    > Sie können die <xref:System.Windows.Controls.GridViewColumn.Width%2A> -Eigenschaft auf `Double.NaN` festlegen, um denselben Effekt zu erzielen.  
  
- **Zeilenelemente auswählen**  
  
     Benutzer können ein oder mehrere Elemente in einer <xref:System.Windows.Controls.GridView>auswählen.  
  
     Informationen zum Ändern der <xref:System.Windows.Style> eines ausgewählten Elements finden Sie unter Verwenden von [Triggern zum Formatieren ausgewählter Elemente in einer ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scrollen Sie, um Inhalt anzuzeigen, der ursprünglich nicht auf dem Bildschirm angezeigt wurde.**  
  
     Wenn die Größe des <xref:System.Windows.Controls.GridView> nicht groß genug ist, um alle Elemente anzuzeigen, können Benutzer mithilfe von Scrollleisten, die von einem <xref:System.Windows.Controls.ScrollViewer> Steuerelement bereitgestellt werden, horizontal oder vertikal scrollen. Eine <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der gesamte Inhalt in einer bestimmten Richtung sichtbar ist. Spaltenheader werden nur beim horizontalen Scrollen und nicht beim vertikalen Scrollen mitbewegt.  
  
- **Interagieren mit Spalten durch Klicken auf die Spaltenheader-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader-Schaltfläche klicken, können sie die Daten sortieren, die in der Spalte angezeigt werden. Dazu müssen Sie jedoch einen Sortieralgorithmus bereitgestellt haben.  
  
     Sie können das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für Spaltenheader-Schaltflächen behandeln, um Funktionen wie einen Sortierungs Algorithmus bereitzustellen. Um das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für einen einzelnen Spaltenheader zu behandeln, legen Sie einen Ereignis <xref:System.Windows.Controls.GridViewColumnHeader>Handler für fest. Um einen Ereignishandler festzulegen, der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> das-Ereignis für alle Spaltenheader behandelt, legen Sie <xref:System.Windows.Controls.ListView> den-Handler für das-Steuerelement fest.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Abrufen anderer benutzerdefinierter Ansichten  
 Die <xref:System.Windows.Controls.GridView> -Klasse, die von der <xref:System.Windows.Controls.ViewBase> abstrakten-Klasse abgeleitet wird, ist nur einer der möglichen Ansichtsmodi <xref:System.Windows.Controls.ListView> für die-Klasse. Sie können andere benutzerdefinierte Ansichten für <xref:System.Windows.Controls.ListView> erstellen, indem Sie <xref:System.Windows.Controls.ViewBase> von der-Klasse ableiten. Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Steuerelement](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>GridView-unterstützende Klassen  
 Die folgenden Klassen unterstützen <xref:System.Windows.Controls.GridView> den Ansichtsmodus.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Übersicht über ListView](listview-overview.md)
- [Sortieren einer GridView-Spalte beim Klicken auf einen Header](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Themen zu Vorgehensweisen](listview-how-to-topics.md)
