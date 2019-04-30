---
title: Übersicht über GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: d2f55db90fb130416ee4dcb15d440b6d367c0b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008762"
---
# <a name="gridview-overview"></a>Übersicht über GridView
<xref:System.Windows.Controls.GridView> Modus der Listenansicht ist einer der Ansichtsmodi für eine <xref:System.Windows.Controls.ListView> Steuerelement. Die <xref:System.Windows.Controls.GridView> -Klasse und die unterstützenden Klassen ermöglichen Ihnen und Ihren Benutzern um Element Auflistungen in einer Tabelle anzuzeigen, die in der Regel Schaltflächen als interaktive Spaltenheader verwendet. In diesem Thema werden die <xref:System.Windows.Controls.GridView> Klasse und ihre Verwendung erläutert.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Was ist eine GridView-Ansicht?  
 Die <xref:System.Windows.Controls.GridView> Ansicht Modus zeigt eine Liste von Datenelementen aus, indem Datenfelder an Spalten binden und ein Spaltenheader zur Identifizierung des Felds angezeigt. Der Standardwert <xref:System.Windows.Controls.GridView> Format implementiert Schaltflächen als Spaltenheader. Mithilfe der Schaltflächen für die Spaltenüberschriften können Sie wichtige Funktionen implementieren; Benutzer können beispielsweise die Spaltenüberschrift zum Sortieren klicken <xref:System.Windows.Controls.GridView> Daten gemäß den Inhalt einer bestimmten Spalte.  
  
> [!NOTE]
>  Das Schaltflächen-Steuerelemente, die <xref:System.Windows.Controls.GridView> verwendeten davon abgeleitet sind <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.GridView> Ansicht <xref:System.Windows.Controls.ListView> Inhalt.  
    
 ![Screenshot mit GridView-Ansicht von ListView-Inhalten.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView> Spalten werden durch dargestellt <xref:System.Windows.Controls.GridViewColumn> -Objekte, die automatisch an ihren Inhalt anpassen können. Optional können Sie explizit festlegen einer <xref:System.Windows.Controls.GridViewColumn> auf eine bestimmte Breite. Sie können die Spaltenbreite mithilfe der Ziehelemente zwischen den Spaltenheadern anpassen. Sie können auch dynamisch hinzufügen, entfernen, ersetzen, und Spalten neu anordnen, da diese Funktionalität ist in integriert <xref:System.Windows.Controls.GridView>. Allerdings <xref:System.Windows.Controls.GridView> kann nicht direkt aktualisiert werden die Daten, das es anzeigt.  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> , die Mitarbeiterdaten anzeigt. In diesem Beispiel <xref:System.Windows.Controls.ListView> definiert die `EmployeeInfoDataSource` als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Die Eigenschaftendefinitionen von <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> binden <xref:System.Windows.Controls.GridViewColumn> Inhalte `EmployeeInfoDataSource` Datenkategorien.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die nachstehende Abbildung zeigt die Tabelle, die mit dem vorherigen Beispiel erstellt wurde. Das GridView-Steuerelement zeigt Daten aus einem ItemsSource-Objekt:
    
 ![Screenshot mit einer ListView mit GridView-Ausgabe.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>GridView-Layout und Stil  
 Die Spaltenzellen und der Kopfzeile der Spalte von einem <xref:System.Windows.Controls.GridViewColumn> die gleiche Breite aufweisen. Standardmäßig ist jede Spalte so breit wie ihr Inhalt. Optional können Sie für eine Spalte auch eine feste Breite angeben.  
  
 Zusammengehörige Dateninhalte werden in horizontalen Zeilen angezeigt. Beispielsweise werden in der vorstehenden Abbildung Vorname, Nachname und ID eines Angestellten als ein Satz angezeigt, da sie sich in einer horizontalen Zeile befinden.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definieren und Formatieren von Spalten in einer GridView-Ansicht  
 Wenn Sie das Datenfeld anzuzeigenden definieren eine <xref:System.Windows.Controls.GridViewColumn>, verwenden die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, oder <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> Eigenschaften. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft Vorrang gegenüber den beiden Eigenschaften der Vorlage.  
  
 Die Ausrichtung des Inhalts in einer Spalte an eine <xref:System.Windows.Controls.GridView>, definieren eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>. Verwenden Sie nicht die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften für <xref:System.Windows.Controls.ListView> mit angezeigten Inhalt eine <xref:System.Windows.Controls.GridView>.  
  
 Um Vorlagen- und Stileigenschaften für die Spaltenüberschriften anzugeben, verwenden Sie die <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, und <xref:System.Windows.Controls.GridViewColumnHeader> Klassen. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Hinzufügen von visuellen Elementen zu einer GridView-Ansicht  
 Um visuelle Elemente hinzuzufügen, wie z. B. <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.Button> gesteuert wird, zu einem <xref:System.Windows.Controls.GridView> Modus anzuzeigen, verwenden Sie Vorlagen oder Stile.  
  
 Wenn Sie ein visuelles Element explizit als Datenelement definieren, darf es nur ein Mal in einer <xref:System.Windows.Controls.GridView>. Diese Einschränkung besteht, weil ein Element nur ein übergeordnetes Element haben und deshalb auch nur ein Mal in der visuellen Struktur angezeigt werden kann.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Formatieren von Zeilen in einer GridView-Ansicht  
 Verwenden der <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Klassen zum Formatieren und Anzeigen der Datenzeilen ein <xref:System.Windows.Controls.GridView>. Ein Beispiel dafür, wie Zeilen in einer <xref:System.Windows.Controls.GridView> Modus anzeigen, finden Sie unter [Formatieren einer Zeile in einem ListView, implementiert eine GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um Ausrichtungsprobleme zwischen Spaltenheadern und Zellen zu vermeiden, keine Eigenschaft festlegen, oder geben Sie eine Vorlage, die die Breite eines Elements in wirkt sich auf eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Z. B. nicht festgelegt die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft, oder geben Sie eine <xref:System.Windows.Controls.ControlTemplate> , addiert einen <xref:System.Windows.Controls.CheckBox> auf eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> , definiert ist, auf eine <xref:System.Windows.Controls.ListView> Steuerelement. Geben Sie stattdessen die Eigenschaften und Vorlagen, die Spaltenbreite direkt bei Klassen beeinflussen, die definieren, eine <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
 Z. B. Hinzufügen einer <xref:System.Windows.Controls.CheckBox> auf die Zeilen in <xref:System.Windows.Controls.GridView> Modus anzeigen, Hinzufügen der <xref:System.Windows.Controls.CheckBox> auf eine <xref:System.Windows.DataTemplate>, und legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft, die <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Benutzerinteraktionen mit einer GridView-Ansicht  
 Bei Verwendung einer <xref:System.Windows.Controls.GridView> in Ihrer Anwendung zu Benutzern interagieren und ändern Sie die Formatierung von der <xref:System.Windows.Controls.GridView>. Benutzer können z.B. Spalten neu anordnen, vergrößern und verkleinern, Elemente in einer Tabelle auswählen und durch Tabelleninhalte scrollen. Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader-Schaltfläche klickt. Der Ereignishandler kann Vorgänge wie das Sortieren der Daten, die in angezeigt wird der <xref:System.Windows.Controls.GridView> entsprechend den Inhalten einer Spalte.  
  
 In der folgende Liste wird ausführlich erläutert, das die Funktionen der Verwendung von <xref:System.Windows.Controls.GridView> seitens der Benutzer:  
  
- **Neuanordnen von Spalten mithilfe der Drag & Drop-Methode**  
  
     Benutzer können Neuanordnen von Spalten in einer <xref:System.Windows.Controls.GridView> durch die linke Maustaste drückt, während er sich über eine Spaltenüberschrift befindet, und klicken Sie dann die Spalte in eine neue Position ziehen. Während der Benutzer den Spaltenheader zieht, wird eine schwebende Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die anzeigt, wo die Spalte eingefügt wird.  
  
     Wenn Sie den Standardstil für schwebenden Version eines Headers ändern möchten, geben Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.GridViewColumnHeader> -Typ, ausgelöst, wenn die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView-Spaltenheader](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Anpassen einer Spalte an ihren Inhalt**  
  
     Benutzer können durch einen Doppelklick auf die Ziehpunkte rechts neben Spaltenheadern Spalten an ihren Inhalt anpassen.  
  
    > [!NOTE]
    >  Sie können festlegen, die <xref:System.Windows.Controls.GridViewColumn.Width%2A> Eigenschaft `Double.NaN` auf dieselbe Wirkung erzielt wird.  
  
- **Zeilenelemente auswählen**  
  
     Benutzer können ein oder mehrere Elemente in Auswählen einer <xref:System.Windows.Controls.GridView>.  
  
     Wenn Sie ändern möchten die <xref:System.Windows.Style> eines ausgewählten Elements finden Sie unter [Verwenden von Triggern zum Formatieren ausgewählter Elemente in einer ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scrollen Sie, um Inhalt anzuzeigen, der ursprünglich nicht auf dem Bildschirm angezeigt wurde.**  
  
     Wenn die Größe der <xref:System.Windows.Controls.GridView> ist nicht groß genug für alle Elemente anzuzeigen, Benutzer können einen horizontalen Bildlauf durchführen oder vertikale Scrollleisten verwenden, die im Lieferumfang von einer <xref:System.Windows.Controls.ScrollViewer> Steuerelement. Ein <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der gesamte Inhalt in einer bestimmten Richtung angezeigt wird. Spaltenheader werden nur beim horizontalen Scrollen und nicht beim vertikalen Scrollen mitbewegt.  
  
- **Interagieren mit Spalten durch Klicken auf die Spaltenheader-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader-Schaltfläche klicken, können sie die Daten sortieren, die in der Spalte angezeigt werden. Dazu müssen Sie jedoch einen Sortieralgorithmus bereitgestellt haben.  
  
     Können Sie behandeln die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für Spaltenheader-Schaltflächen um Funktionen wie einen Sortieralgorithmus zu bieten. Behandelt die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für einen einzelnen Spaltenkopf, legen Sie einen Ereignishandler für die <xref:System.Windows.Controls.GridViewColumnHeader>. Um einen Ereignishandler festzulegen, behandelt der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für alle Spaltenheader, legen Sie den Handler für die <xref:System.Windows.Controls.ListView> Steuerelement.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Abrufen anderer benutzerdefinierter Ansichten  
 Die <xref:System.Windows.Controls.GridView> -Klasse, die von abgeleitet ist die <xref:System.Windows.Controls.ViewBase> abstrakte Klasse, ist nur einer der Ansichtsmodi für die <xref:System.Windows.Controls.ListView> Klasse. Sie können für andere benutzerdefinierte Ansichten erstellen <xref:System.Windows.Controls.ListView> durch Ableiten von der <xref:System.Windows.Controls.ViewBase> Klasse. Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Steuerelement](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>GridView-unterstützende Klassen  
 Die folgenden Klassen unterstützen die <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
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
