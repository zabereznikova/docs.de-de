---
title: Übersicht über GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181891"
---
# <a name="gridview-overview"></a>Übersicht über GridView
<xref:System.Windows.Controls.GridView>Ansichtsmodus ist einer der Ansichtsmodi für ein <xref:System.Windows.Controls.ListView> Steuerelement. Die <xref:System.Windows.Controls.GridView> Klasse und ihre unterstützenden Klassen ermöglichen es Ihnen und Ihren Benutzern, Elementsammlungen in einer Tabelle anzuzeigen, die in der Regel Schaltflächen als interaktive Spaltenüberschriften verwendet. In diesem <xref:System.Windows.Controls.GridView> Thema wird die Klasse vorgestellt und ihre Verwendung beschrieben.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>Was ist eine GridView-Ansicht?  
 Im <xref:System.Windows.Controls.GridView> Ansichtsmodus wird eine Liste von Datenelementen angezeigt, indem Datenfelder an Spalten gebunden und eine Spaltenüberschrift zum Identifizieren des Felds angezeigt wird. Der <xref:System.Windows.Controls.GridView> Standardstil implementiert Schaltflächen als Spaltenüberschriften. Durch die Verwendung von Schaltflächen für Spaltenüberschriften können Sie wichtige Benutzerinteraktionsfunktionen implementieren. Benutzer können beispielsweise auf die Spaltenüberschrift klicken, um Daten nach dem Inhalt einer bestimmten Spalte zu sortieren. <xref:System.Windows.Controls.GridView>  
  
> [!NOTE]
> Die Schaltflächensteuerelemente, die <xref:System.Windows.Controls.GridView> für <xref:System.Windows.Controls.Primitives.ButtonBase>Spaltenüberschriften verwendet werden, werden von abgeleitet.  
  
 Die folgende Abbildung <xref:System.Windows.Controls.GridView> zeigt <xref:System.Windows.Controls.ListView> eine Ansicht des Inhalts.  

 ![Screenshot, der die GridView-Ansicht von ListView-Inhalten anzeigt.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>Spalten werden <xref:System.Windows.Controls.GridViewColumn> durch Objekte dargestellt, die automatisch zu ihrem Inhalt verkleinert werden können. Optional können Sie explizit <xref:System.Windows.Controls.GridViewColumn> eine auf eine bestimmte Breite festlegen. Sie können die Spaltenbreite mithilfe der Ziehelemente zwischen den Spaltenheadern anpassen. Sie können Spalten auch dynamisch hinzufügen, entfernen, ersetzen und <xref:System.Windows.Controls.GridView>neu anordnen, da diese Funktionalität in integriert ist. <xref:System.Windows.Controls.GridView> Die angezeigten Daten können jedoch nicht direkt aktualisiert werden.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.GridView> wie Sie eine definieren, die Mitarbeiterdaten anzeigt. <xref:System.Windows.Controls.ListView> Definiert in diesem Beispiel `EmployeeInfoDataSource` die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>als . Die Eigenschaftsdefinitionen <xref:System.Windows.Controls.GridViewColumn> von `EmployeeInfoDataSource` Bindungsinhalt <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> an Datenkategorien.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die nachstehende Abbildung zeigt die Tabelle, die mit dem vorherigen Beispiel erstellt wurde. Das GridView-Steuerelement zeigt Daten aus einem ItemsSource-Objekt an:

 ![Screenshot, der eine ListView mit GridView-Ausgabe zeigt.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>GridView-Layout und Stil  
 Die Spaltenzellen und der <xref:System.Windows.Controls.GridViewColumn> Spaltenkopf eines haben die gleiche Breite. Standardmäßig ist jede Spalte so breit wie ihr Inhalt. Optional können Sie für eine Spalte auch eine feste Breite angeben.  
  
 Zusammengehörige Dateninhalte werden in horizontalen Zeilen angezeigt. Beispielsweise werden in der vorstehenden Abbildung Vorname, Nachname und ID eines Angestellten als ein Satz angezeigt, da sie sich in einer horizontalen Zeile befinden.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definieren und Formatieren von Spalten in einer GridView-Ansicht  
 Verwenden Sie beim Definieren des <xref:System.Windows.Controls.GridViewColumn>Datenfelds, das in einem angezeigt werden soll, die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>oder <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> Eigenschaften. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft hat Vorrang vor einer der Vorlageneigenschaften.  
  
 Um die Ausrichtung des Inhalts in <xref:System.Windows.Controls.GridView>einer <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>Spalte eines anzugeben, definieren Sie eine . Verwenden Sie <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> die <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> und <xref:System.Windows.Controls.ListView> Eigenschaften nicht für <xref:System.Windows.Controls.GridView>Inhalte, die mithilfe einer angezeigt werden.  
  
 Um Vorlagen- und Stileigenschaften für Spaltenüberschriften anzugeben, verwenden Sie die <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>und <xref:System.Windows.Controls.GridViewColumnHeader> Klassen. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Hinzufügen von visuellen Elementen zu einer GridView-Ansicht  
 Um visuelle Elemente, <xref:System.Windows.Controls.CheckBox> z. B. Steuerelemente, <xref:System.Windows.Controls.Button> zu einem <xref:System.Windows.Controls.GridView> Ansichtsmodus hinzuzufügen, verwenden Sie Vorlagen oder Stile.  
  
 Wenn Sie ein visuelles Element explizit als Datenelement definieren, <xref:System.Windows.Controls.GridView>kann es nur einmal in einem angezeigt werden. Diese Einschränkung besteht, weil ein Element nur ein übergeordnetes Element haben und deshalb auch nur ein Mal in der visuellen Struktur angezeigt werden kann.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Formatieren von Zeilen in einer GridView-Ansicht  
 Verwenden <xref:System.Windows.Controls.GridViewRowPresenter> Sie <xref:System.Windows.Controls.GridViewHeaderRowPresenter> die und-Klassen, um <xref:System.Windows.Controls.GridView>die Zeilen einer zu formatieren und anzuzeigen. Ein Beispiel für das Formatieren <xref:System.Windows.Controls.GridView> von Zeilen in einem Ansichtsmodus finden Sie unter [Stil einer Zeile in einer ListView, die eine GridView implementiert.](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um Ausrichtungsprobleme zwischen Spaltenüberschriften und Zellen zu vermeiden, legen Sie keine Eigenschaft <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>fest, oder geben Sie keine Vorlage an, die sich auf die Breite eines Elements in einem auswirkt. Legen Sie z. <xref:System.Windows.FrameworkElement.Margin%2A> B. keine <xref:System.Windows.Controls.ControlTemplate> Eigenschaft <xref:System.Windows.Controls.CheckBox> fest, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> oder geben <xref:System.Windows.Controls.ListView> Sie keine an, die eine hinzufügt, die für ein Steuerelement definiert ist. Geben Sie stattdessen die Eigenschaften und Vorlagen an, die <xref:System.Windows.Controls.GridView> sich direkt auf die Spaltenbreite für Klassen auswirken, die einen Ansichtsmodus definieren.  
  
 Um z. B. den <xref:System.Windows.Controls.GridView> Zeilen im Ansichtsmodus <xref:System.Windows.DataTemplate>eine <xref:System.Windows.Controls.CheckBox> hinzuzufügen, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> fügen <xref:System.Windows.DataTemplate>Sie die <xref:System.Windows.Controls.CheckBox> zu einem hinzu, und legen Sie dann die Eigenschaft auf diese fest.  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Benutzerinteraktionen mit einer GridView-Ansicht  
 Wenn Sie <xref:System.Windows.Controls.GridView> eine in Ihrer Anwendung verwenden, können Benutzer <xref:System.Windows.Controls.GridView>mit der interagieren und diese ändern. Benutzer können z.B. Spalten neu anordnen, vergrößern und verkleinern, Elemente in einer Tabelle auswählen und durch Tabelleninhalte scrollen. Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader-Schaltfläche klickt. Der Ereignishandler kann Vorgänge wie das Sortieren <xref:System.Windows.Controls.GridView> der Daten ausführen, die entsprechend dem Inhalt einer Spalte angezeigt werden.  
  
 In der folgenden Liste werden die <xref:System.Windows.Controls.GridView> Funktionen der Verwendung für die Benutzerinteraktion ausführlicher erläutert:  
  
- **Neuanordnen von Spalten mithilfe der Drag & Drop-Methode**  
  
     Benutzer können Spalten in <xref:System.Windows.Controls.GridView> einem neu anordnen, indem sie die linke Maustaste drücken, während sie sich über einer Spaltenüberschrift befindet, und diese Spalte dann an eine neue Position ziehen. Während der Benutzer den Spaltenheader zieht, wird eine schwebende Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die anzeigt, wo die Spalte eingefügt wird.  
  
     Wenn Sie den Standardstil für die unverankerte Version <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.GridViewColumnHeader> Headers ändern <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> möchten, geben <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>Sie eine für einen Typ an, der ausgelöst wird, wenn die Eigenschaft auf festgelegt wird. Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView-Spaltenheader](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Anpassen einer Spalte an ihren Inhalt**  
  
     Benutzer können durch einen Doppelklick auf die Ziehpunkte rechts neben Spaltenheadern Spalten an ihren Inhalt anpassen.  
  
    > [!NOTE]
    > Sie können <xref:System.Windows.Controls.GridViewColumn.Width%2A> die `Double.NaN` Eigenschaft so festlegen, dass sie denselben Effekt erzeugt.  
  
- **Zeilenelemente auswählen**  
  
     Benutzer können ein oder mehrere <xref:System.Windows.Controls.GridView>Elemente in einer auswählen.  
  
     Wenn Sie das <xref:System.Windows.Style> ausgewählte Element ändern möchten, finden Sie weitere Informationen unter Verwenden von [Triggern zum Stil ausgewählter Elemente in einer ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scrollen Sie, um Inhalt anzuzeigen, der ursprünglich nicht auf dem Bildschirm angezeigt wurde.**  
  
     Wenn die Größe <xref:System.Windows.Controls.GridView> des nicht groß genug ist, um alle Elemente anzuzeigen, können Benutzer horizontal oder <xref:System.Windows.Controls.ScrollViewer> vertikal mit Bildlaufleisten scrollen, die von einem Steuerelement bereitgestellt werden. A <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der gesamte Inhalt in eine bestimmte Richtung sichtbar ist. Spaltenheader werden nur beim horizontalen Scrollen und nicht beim vertikalen Scrollen mitbewegt.  
  
- **Interagieren mit Spalten durch Klicken auf die Spaltenheader-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader-Schaltfläche klicken, können sie die Daten sortieren, die in der Spalte angezeigt werden. Dazu müssen Sie jedoch einen Sortieralgorithmus bereitgestellt haben.  
  
     Sie können <xref:System.Windows.Controls.Primitives.ButtonBase.Click> das Ereignis für Spaltenkopfschaltflächen behandeln, um Funktionen wie einen Sortieralgorithmus bereitzustellen. Um das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis für einen einzelnen Spaltenheader zu <xref:System.Windows.Controls.GridViewColumnHeader>behandeln, legen Sie einen Ereignishandler für die fest. Um einen Ereignishandler festzulegen, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> der das Ereignis für alle Spaltenüberschriften behandelt, legen Sie den Handler für das <xref:System.Windows.Controls.ListView> Steuerelement fest.  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Abrufen anderer benutzerdefinierter Ansichten  
 Die <xref:System.Windows.Controls.GridView> Klasse, die von <xref:System.Windows.Controls.ViewBase> der abstrakten Klasse abgeleitet wird, ist <xref:System.Windows.Controls.ListView> nur einer der möglichen Ansichtsmodi für die Klasse. Sie können andere benutzerdefinierte Ansichten für <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ViewBase> erstellen, indem Sie von der Klasse ableiten. Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Steuerelement](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>GridView-unterstützende Klassen  
 Die folgenden Klassen <xref:System.Windows.Controls.GridView> unterstützen den Ansichtsmodus.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Übersicht über ListView](listview-overview.md)
- [Sortieren einer GridView-Spalte beim Klicken auf einen Header](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [How-to-Themen](listview-how-to-topics.md)
