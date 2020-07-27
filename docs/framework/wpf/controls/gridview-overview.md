---
title: Übersicht über GridView
description: Erfahren Sie mehr über Stile und Vorlagen für das Windows Presentation Foundation ListView-Steuerelement. Ändern Sie ControlTemplate, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 02a2182ef1fc893107e434f431b9fbe0b3fbcd08
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165930"
---
# <a name="gridview-overview"></a>Übersicht über GridView
<xref:System.Windows.Controls.GridView>der Ansichtsmodus ist einer der Ansichtsmodi für ein <xref:System.Windows.Controls.ListView> Steuerelement. Mithilfe der <xref:System.Windows.Controls.GridView> -Klasse und der unterstützenden Klassen können Sie und Ihre Benutzer Element Auflistungen in einer Tabelle anzeigen, in der normalerweise Schaltflächen als interaktive Spaltenheader verwendet werden. In diesem Thema wird die <xref:System.Windows.Controls.GridView> -Klasse vorgestellt und deren Verwendung beschrieben.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>Was ist eine GridView-Ansicht?  
 Im <xref:System.Windows.Controls.GridView> Ansichtsmodus wird eine Liste von Datenelementen angezeigt, indem Datenfelder an Spalten gebunden werden und ein Spaltenheader zum Identifizieren des Felds angezeigt wird. Der Standard <xref:System.Windows.Controls.GridView> Stil implementiert Schaltflächen als Spaltenheader. Mithilfe von Schaltflächen für Spaltenkopfzeilen können Sie wichtige Funktionen für die Benutzerinteraktion implementieren. Beispielsweise können Benutzer auf die Spaltenüberschrift klicken, um die <xref:System.Windows.Controls.GridView> Daten nach dem Inhalt einer bestimmten Spalte zu sortieren.  
  
> [!NOTE]
> Die Schaltflächen-Steuerelemente, die <xref:System.Windows.Controls.GridView> für Spaltenheader verwendet, werden von abgeleitet <xref:System.Windows.Controls.Primitives.ButtonBase> .  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.GridView> Inhaltsansicht <xref:System.Windows.Controls.ListView> .  

 ![Screenshot, der die GridView-Ansicht von ListView-Inhalt anzeigt.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>Spalten werden durch- <xref:System.Windows.Controls.GridViewColumn> Objekte dargestellt, die automatisch an ihren Inhalt anpassen können. Optional können Sie einen explizit <xref:System.Windows.Controls.GridViewColumn> auf eine bestimmte Breite festlegen. Sie können die Spaltenbreite mithilfe der Ziehelemente zwischen den Spaltenheadern anpassen. Sie können Spalten auch dynamisch hinzufügen, entfernen, ersetzen und neu anordnen, da diese Funktionalität in integriert ist <xref:System.Windows.Controls.GridView> . Die angezeigten <xref:System.Windows.Controls.GridView> Daten können jedoch nicht direkt aktualisiert werden.  
  
 Im folgenden Beispiel wird gezeigt, wie ein definiert wird <xref:System.Windows.Controls.GridView> , das Mitarbeiterdaten anzeigt. In diesem Beispiel <xref:System.Windows.Controls.ListView> definiert das `EmployeeInfoDataSource` als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> . Die Eigenschafts Definitionen von <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Binden von <xref:System.Windows.Controls.GridViewColumn> Inhalten an `EmployeeInfoDataSource` Datenkategorien.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die nachstehende Abbildung zeigt die Tabelle, die mit dem vorherigen Beispiel erstellt wurde. Das GridView-Steuerelement zeigt Daten aus einem ItemsSource-Objekt an:

 ![Screenshot, der eine ListView mit GridView-Ausgabe zeigt.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>GridView-Layout und Stil  
 Die Spalten Zellen und der Spaltenheader eines <xref:System.Windows.Controls.GridViewColumn> haben dieselbe Breite. Standardmäßig ist jede Spalte so breit wie ihr Inhalt. Optional können Sie für eine Spalte auch eine feste Breite angeben.  
  
 Zusammengehörige Dateninhalte werden in horizontalen Zeilen angezeigt. Beispielsweise werden in der vorstehenden Abbildung Vorname, Nachname und ID eines Angestellten als ein Satz angezeigt, da sie sich in einer horizontalen Zeile befinden.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definieren und Formatieren von Spalten in einer GridView-Ansicht  
 Wenn Sie das Datenfeld definieren, das in einem angezeigt <xref:System.Windows.Controls.GridViewColumn> werden soll, verwenden Sie die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaften, oder <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> . Die- <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft hat Vorrang vor den Vorlagen Eigenschaften.  
  
 Um die Ausrichtung des Inhalts in einer Spalte einer anzugeben <xref:System.Windows.Controls.GridView> , definieren Sie eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> . Verwenden Sie die-Eigenschaft und die-Eigenschaft nicht <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> für <xref:System.Windows.Controls.ListView> Inhalte, die mit einem angezeigt werden <xref:System.Windows.Controls.GridView> .  
  
 Um Vorlagen-und Stileigenschaften für Spaltenheader anzugeben, verwenden Sie die <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn> Klassen, und <xref:System.Windows.Controls.GridViewColumnHeader> . Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Hinzufügen von visuellen Elementen zu einer GridView-Ansicht  
 Verwenden Sie Vorlagen oder Stile, um visuelle Elemente, wie z. b. <xref:System.Windows.Controls.CheckBox> -und-Steuerelemente <xref:System.Windows.Controls.Button> , zu einem <xref:System.Windows.Controls.GridView> Anzeigemodus hinzuzufügen.  
  
 Wenn Sie ein visuelles Element explizit als Datenelement definieren, kann es nur einmal in einem Vorkommen <xref:System.Windows.Controls.GridView> . Diese Einschränkung besteht, weil ein Element nur ein übergeordnetes Element haben und deshalb auch nur ein Mal in der visuellen Struktur angezeigt werden kann.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Formatieren von Zeilen in einer GridView-Ansicht  
 Verwenden <xref:System.Windows.Controls.GridViewRowPresenter> Sie die <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Klassen und, um die Zeilen eines zu formatieren und anzuzeigen <xref:System.Windows.Controls.GridView> . Ein Beispiel für das Formatieren von Zeilen in einem <xref:System.Windows.Controls.GridView> Ansichtsmodus finden Sie unter Formatieren [einer Zeile in einem ListView-Steuer Punkt, der eine GridView implementiert](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um Ausrichtungs Probleme zwischen Spaltenüberschriften und Zellen zu vermeiden, legen Sie keine Eigenschaft fest, oder geben Sie eine Vorlage an, die sich auf die Breite eines Elements in einem auswirkt <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Legen Sie beispielsweise die-Eigenschaft nicht fest, oder geben Sie einen an, der ein-Element einem <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.ControlTemplate> hinzufügt, <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> das in einem-Steuerelement definiert ist <xref:System.Windows.Controls.ListView> . Geben Sie stattdessen die Eigenschaften und Vorlagen, die die Spaltenbreite betreffen, direkt auf Klassen an, die einen <xref:System.Windows.Controls.GridView> Ansichtsmodus definieren.  
  
 Wenn Sie z. b. <xref:System.Windows.Controls.CheckBox> der Zeilen im Ansichtsmodus einen hinzufügen möchten <xref:System.Windows.Controls.GridView> , fügen Sie den <xref:System.Windows.Controls.CheckBox> zu einem hinzu <xref:System.Windows.DataTemplate> , und legen Sie dann die- <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft auf fest <xref:System.Windows.DataTemplate> .  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Benutzerinteraktionen mit einer GridView-Ansicht  
 Wenn Sie <xref:System.Windows.Controls.GridView> in Ihrer Anwendung verwenden, können Benutzer mit interagieren und die Formatierung von ändern <xref:System.Windows.Controls.GridView> . Benutzer können z.B. Spalten neu anordnen, vergrößern und verkleinern, Elemente in einer Tabelle auswählen und durch Tabelleninhalte scrollen. Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader-Schaltfläche klickt. Der Ereignishandler kann Vorgänge wie das Sortieren der Daten ausführen, die in der <xref:System.Windows.Controls.GridView> entsprechend dem Inhalt einer Spalte angezeigt werden.  
  
 In der folgenden Liste werden die Funktionen der Verwendung von <xref:System.Windows.Controls.GridView> für die Benutzerinteraktion ausführlicher erläutert:  
  
- **Neuanordnen von Spalten mithilfe der Drag & Drop-Methode**  
  
     Benutzer können Spalten in einer neu anordnen, <xref:System.Windows.Controls.GridView> indem Sie die linke Maustaste gedrückt halten, während Sie sich über einem Spaltenheader befindet, und dann diese Spalte an eine neue Position ziehen. Während der Benutzer den Spaltenheader zieht, wird eine schwebende Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die anzeigt, wo die Spalte eingefügt wird.  
  
     Wenn Sie den Standardstil für die unverankerte Version eines Headers ändern möchten, geben Sie einen <xref:System.Windows.Controls.ControlTemplate> für einen Typ an, <xref:System.Windows.Controls.GridViewColumnHeader> der ausgelöst wird, wenn die- <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> . Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView-Spaltenheader](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Anpassen einer Spalte an ihren Inhalt**  
  
     Benutzer können durch einen Doppelklick auf die Ziehpunkte rechts neben Spaltenheadern Spalten an ihren Inhalt anpassen.  
  
    > [!NOTE]
    > Sie können die- <xref:System.Windows.Controls.GridViewColumn.Width%2A> Eigenschaft auf festlegen, `Double.NaN` um denselben Effekt zu erzielen.  
  
- **Zeilenelemente auswählen**  
  
     Benutzer können ein oder mehrere Elemente in einer auswählen <xref:System.Windows.Controls.GridView> .  
  
     Informationen zum Ändern der <xref:System.Windows.Style> eines ausgewählten Elements finden Sie unter Verwenden von [Triggern zum Formatieren ausgewählter Elemente in einer ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scrollen Sie, um Inhalt anzuzeigen, der ursprünglich nicht auf dem Bildschirm angezeigt wurde.**  
  
     Wenn die Größe des <xref:System.Windows.Controls.GridView> nicht groß genug ist, um alle Elemente anzuzeigen, können Benutzer mithilfe von Scrollleisten, die von einem Steuerelement bereitgestellt werden, horizontal oder vertikal scrollen <xref:System.Windows.Controls.ScrollViewer> . Eine <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der gesamte Inhalt in einer bestimmten Richtung sichtbar ist. Spaltenheader werden nur beim horizontalen Scrollen und nicht beim vertikalen Scrollen mitbewegt.  
  
- **Interagieren mit Spalten durch Klicken auf die Spaltenheader-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader-Schaltfläche klicken, können sie die Daten sortieren, die in der Spalte angezeigt werden. Dazu müssen Sie jedoch einen Sortieralgorithmus bereitgestellt haben.  
  
     Sie können das- <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis für Spaltenheader-Schaltflächen behandeln, um Funktionen wie einen Sortierungs Algorithmus bereitzustellen. Um das- <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis für einen einzelnen Spaltenheader zu behandeln, legen Sie einen Ereignishandler für fest <xref:System.Windows.Controls.GridViewColumnHeader> . Um einen Ereignishandler festzulegen, der das- <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis für alle Spaltenheader behandelt, legen Sie den-Handler für das-Steuerelement fest <xref:System.Windows.Controls.ListView> .  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Abrufen anderer benutzerdefinierter Ansichten  
 Die- <xref:System.Windows.Controls.GridView> Klasse, die von der abstrakten-Klasse abgeleitet wird <xref:System.Windows.Controls.ViewBase> , ist nur einer der möglichen Ansichtsmodi für die- <xref:System.Windows.Controls.ListView> Klasse. Sie können andere benutzerdefinierte Ansichten für erstellen, <xref:System.Windows.Controls.ListView> indem Sie von der- <xref:System.Windows.Controls.ViewBase> Klasse ableiten. Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Steuerelement](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>GridView-unterstützende Klassen  
 Die folgenden Klassen unterstützen den <xref:System.Windows.Controls.GridView> Ansichtsmodus.  
  
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
- [Artikel zu Vorgehensweisen](listview-how-to-topics.md)
