---
title: "Übersicht über GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 44574b5737873371f9a7bc9be2d851a8ae1e101b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gridview-overview"></a>Übersicht über GridView
<xref:System.Windows.Controls.GridView>Ansichtsmodus ist einer der Ansichtsmodi für ein <xref:System.Windows.Controls.ListView> Steuerelement. Die <xref:System.Windows.Controls.GridView> -Klasse und unterstützenden Klassen aktivieren Sie und Ihre Benutzer Element Auflistungen in einer Tabelle anzuzeigen, die Schaltflächen in der Regel als interaktive Spaltenüberschriften verwendet. Dieses Thema enthält die <xref:System.Windows.Controls.GridView> Klasse und ihre Verwendung erläutert.  
  
  
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Was ist eine GridView-Ansicht?  
 Die <xref:System.Windows.Controls.GridView> Ansicht Modus zeigt eine Liste von Datenelementen aus, indem Binden von Daten von Feldern zu Spalten und einen Spaltenheader zur Identifizierung des Felds angezeigt. Die Standardeinstellung <xref:System.Windows.Controls.GridView> -Stil implementiert Schaltflächen als Spaltenüberschriften. Mithilfe der Schaltflächen für die Spaltenkopfzeilen können Sie wichtige interaktive Benutzerfunktionen implementieren; Beispielsweise können Benutzer den Spaltenüberschrift zum Sortieren klicken <xref:System.Windows.Controls.GridView> Daten entsprechend den Inhalten der einer bestimmten Spalte.  
  
> [!NOTE]
>  Die Schaltflächen-Steuerelemente, die <xref:System.Windows.Controls.GridView> verwendet für die Spaltenkopfzeilen abgeleitet sind <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.GridView> Ansicht <xref:System.Windows.Controls.ListView> Inhalt.  
  
 **GridView-Ansicht von ListView-Inhalt**  
  
 ![Mit einem Stil versehene ListView-Ansicht](../../../../docs/framework/wpf/controls/media/styledlistview.PNG "Mit einem Stil versehene ListView-Ansicht")  
  
 <xref:System.Windows.Controls.GridView>Spalten werden durch dargestellt <xref:System.Windows.Controls.GridViewColumn> Objekte, die auf ihre Inhalte automatisch angepasst werden können. Optional können Sie explizit festlegen einer <xref:System.Windows.Controls.GridViewColumn> zu einer bestimmten Breite. Sie können die Spaltenbreite mithilfe der Ziehelemente zwischen den Spaltenheadern anpassen. Sie können auch dynamisch hinzufügen, entfernen Sie ersetzen und Neuanordnen von Spalten, da diese Funktionalität ist in integriert <xref:System.Windows.Controls.GridView>. Allerdings <xref:System.Windows.Controls.GridView> kann nicht direkt aktualisieren Sie die Daten, die es anzeigt.  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> , die Mitarbeiterdaten anzeigt. In diesem Beispiel <xref:System.Windows.Controls.ListView> definiert die `EmployeeInfoDataSource` als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Die Eigenschaftsdefinitionen der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> binden <xref:System.Windows.Controls.GridViewColumn> Inhalt `EmployeeInfoDataSource` Datenkategorien.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die nachstehende Abbildung zeigt die Tabelle, die mit dem vorherigen Beispiel erstellt wurde.  
  
 **GridView-Ansicht, die Daten aus ItemsSource anzeigt**  
  
 ![ListView mit GridView-Ausgabe](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>GridView-Layout und Stil  
 Die Zellen der Spalte und die Spaltenüberschrift der eine <xref:System.Windows.Controls.GridViewColumn> weisen die gleiche Breite. Standardmäßig ist jede Spalte so breit wie ihr Inhalt. Optional können Sie für eine Spalte auch eine feste Breite angeben.  
  
 Zusammengehörige Dateninhalte werden in horizontalen Zeilen angezeigt. Beispielsweise werden in der vorstehenden Abbildung Vorname, Nachname und ID eines Angestellten als ein Satz angezeigt, da sie sich in einer horizontalen Zeile befinden.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definieren und Formatieren von Spalten in einer GridView-Ansicht  
 Wenn Sie das Feld "Daten" anzuzeigenden definieren eine <xref:System.Windows.Controls.GridViewColumn>, verwenden Sie die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, oder <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> Eigenschaften. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft hat Vorrang vor einer der Eigenschaften der Vorlage.  
  
 An die Ausrichtung von Inhalt in einer Spalte mit einem <xref:System.Windows.Controls.GridView>, definieren eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>. Verwenden Sie nicht die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> und <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> Eigenschaften für <xref:System.Windows.Controls.ListView> mit angezeigten Inhalt eine <xref:System.Windows.Controls.GridView>.  
  
 Verwenden Sie zum Angeben der Vorlage und des Stils Eigenschaften für die Spaltenkopfzeilen der <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, und <xref:System.Windows.Controls.GridViewColumnHeader> Klassen. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Hinzufügen von visuellen Elementen zu einer GridView-Ansicht  
 Um visuelle Elemente hinzufügen, z. B. <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.Button> Steuerelemente, die zu einem <xref:System.Windows.Controls.GridView> Modus anzuzeigen, verwenden Sie Vorlagen oder Stile.  
  
 Wenn Sie ein visuelles Element explizit als ein Datenelement definieren, stehen sie nur ein Mal in einer <xref:System.Windows.Controls.GridView>. Diese Einschränkung besteht, weil ein Element nur ein übergeordnetes Element haben und deshalb auch nur ein Mal in der visuellen Struktur angezeigt werden kann.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Formatieren von Zeilen in einer GridView-Ansicht  
 Verwenden der <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Klassen zum Formatieren und Anzeigen der Datenzeilen ein <xref:System.Windows.Controls.GridView>. Ein Beispiel dafür, wie Zeilen in einem <xref:System.Windows.Controls.GridView> Modus anzuzeigen, finden Sie unter [formatieren eine Zeile in einem ListView, implementiert eine GridView](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um zu verhindern, dass Ausrichtungsprobleme zwischen den Spaltenüberschriften und Zellen, keine Eigenschaft festlegen, oder geben Sie eine Vorlage, die die Breite eines Elements in wirkt sich auf eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Legen Sie z. B. nicht die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft, oder geben Sie eine <xref:System.Windows.Controls.ControlTemplate> , addiert eine <xref:System.Windows.Controls.CheckBox> auf ein <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf definiert ist eine <xref:System.Windows.Controls.ListView> Steuerelement. Geben Sie stattdessen die Eigenschaften und Vorlagen, die Spaltenbreite direkt auf Klassen, die definieren, beeinflussen eine <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
 Z. B. Hinzufügen einer <xref:System.Windows.Controls.CheckBox> auf die Zeilen in <xref:System.Windows.Controls.GridView> Modus anzeigen, Hinzufügen der <xref:System.Windows.Controls.CheckBox> auf eine <xref:System.Windows.DataTemplate>, und legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft mit <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Benutzerinteraktionen mit einer GridView-Ansicht  
 Bei Verwendung einer <xref:System.Windows.Controls.GridView> in Ihrer Anwendung Benutzer interagieren können, und ändern Sie die Formatierung der der <xref:System.Windows.Controls.GridView>. Benutzer können z.B. Spalten neu anordnen, vergrößern und verkleinern, Elemente in einer Tabelle auswählen und durch Tabelleninhalte scrollen. Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader-Schaltfläche klickt. Der Ereignishandler kann Vorgänge wie das Sortieren der Daten, die in angezeigt wird der <xref:System.Windows.Controls.GridView> gemäß den Inhalt einer Spalte.  
  
 In der folgenden Liste wird ausführlicher erläutert, die Funktionen für die Verwendung <xref:System.Windows.Controls.GridView> für Eingreifen des Benutzers:  
  
-   **Neuanordnen von Spalten mithilfe der Drag & Drop-Methode**  
  
     Benutzer können Neuanordnen von Spalten in einer <xref:System.Windows.Controls.GridView> durch Drücken die linke Maustaste gedrückt, während er auf eine Spaltenüberschrift ist, und klicken Sie dann die Spalte an eine neue Position ziehen. Während der Benutzer den Spaltenheader zieht, wird eine schwebende Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die anzeigt, wo die Spalte eingefügt wird.  
  
     Wenn Sie das Standardformat für die unverankerte Version eines Headers ändern möchten, geben Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.GridViewColumnHeader> -Typ, ausgelöst, wenn die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView-Spaltenheader](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Anpassen einer Spalte an ihren Inhalt**  
  
     Benutzer können durch einen Doppelklick auf die Ziehpunkte rechts neben Spaltenheadern Spalten an ihren Inhalt anpassen.  
  
    > [!NOTE]
    >  Sie können festlegen, die <xref:System.Windows.Controls.GridViewColumn.Width%2A> Eigenschaft, um `Double.NaN` auf dieselbe Wirkung erzielt wird.  
  
-   **Zeilenelemente auswählen**  
  
     Wählen Sie Benutzer können ein oder mehrere Elemente in einem <xref:System.Windows.Controls.GridView>.  
  
     Wenn Sie ändern möchten die <xref:System.Windows.Style> eines ausgewählten Elements finden Sie unter [Verwendung von Triggern für Stil aktivierten Elemente in einem ListView](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Scrollen Sie, um Inhalt anzuzeigen, der ursprünglich nicht auf dem Bildschirm angezeigt wurde.**  
  
     Wenn die Größe der <xref:System.Windows.Controls.GridView> ist nicht groß genug für alle Elemente anzuzeigen, die Benutzer können Blättern horizontal oder vertikal mit Bildlaufleisten angezeigt, die im Lieferumfang von einer <xref:System.Windows.Controls.ScrollViewer> Steuerelement. Ein <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der gesamte Inhalt in eine bestimmte Richtung angezeigt wird. Spaltenheader werden nur beim horizontalen Scrollen und nicht beim vertikalen Scrollen mitbewegt.  
  
-   **Interagieren mit Spalten durch Klicken auf die Spaltenheader-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader-Schaltfläche klicken, können sie die Daten sortieren, die in der Spalte angezeigt werden. Dazu müssen Sie jedoch einen Sortieralgorithmus bereitgestellt haben.  
  
     Sie behandeln können die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis für Spaltenheader-Schaltflächen um Funktionen wie eines Sortieralgorithmus bereitzustellen. Behandeln der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für eine einzelne Spalte-Header, legen Sie einen Ereignishandler auf der <xref:System.Windows.Controls.GridViewColumnHeader>. Um einen Ereignishandler festzulegen, behandelt der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für alle Spaltenüberschriften, legen Sie den Ereignishandler für die <xref:System.Windows.Controls.ListView> Steuerelement.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Abrufen anderer benutzerdefinierter Ansichten  
 Die <xref:System.Windows.Controls.GridView> -Klasse, die abgeleitet ist die <xref:System.Windows.Controls.ViewBase> abstrakte Klasse, ist nur eine der möglichen Ansichtsmodi für die <xref:System.Windows.Controls.ListView> Klasse. Sie können andere benutzerdefinierte Ansichten erstellen <xref:System.Windows.Controls.ListView> durch Ableiten von der <xref:System.Windows.Controls.ViewBase> Klasse. Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Steuerelement](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>GridView-unterstützende Klassen  
 Die folgenden Klassen unterstützen die <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Controls.GridViewColumn>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.ViewBase>  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Sortieren einer GridView-Spalte beim Klicken auf einen Header](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
