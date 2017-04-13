---
title: "&#220;bersicht &#252;ber GridView | Microsoft Docs"
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
  - "Steuerelemente, ListView"
  - "GridView-Ansichtsmodus"
  - "ListView-Steuerelemente, GridView-Ansichtsmodus"
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# &#220;bersicht &#252;ber GridView
Der <xref:System.Windows.Controls.GridView>\-Ansichtsmodus ist einer der Ansichtsmodi für ein <xref:System.Windows.Controls.ListView>\-Steuerelement.  Die <xref:System.Windows.Controls.GridView>\-Klasse und ihre unterstützenden Klassen ermöglichen Ihnen und Ihren Benutzern das Anzeigen von Elementauflistungen in einer Tabelle, die in der Regel Schaltflächen als interaktive Spaltenheader verwendet.  Dieses Thema führt die <xref:System.Windows.Controls.GridView>\-Klasse ein und gibt einen Überblick über ihre Verwendung.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## Was ist eine GridView\-Ansicht?  
 Der <xref:System.Windows.Controls.GridView>\-Ansichtsmodus zeigt eine Liste mit Datenelementen an, indem Datenfelder an Spalten gebunden werden und ein Spaltenheader zur Identifizierung des Felds angezeigt wird.  Der Standard\-<xref:System.Windows.Controls.GridView>\-Stil implementiert Schaltflächen als Spaltenheader.  Durch das Verwenden von Schaltflächen für Spaltenheader können Sie wichtige interaktive Benutzerfunktionen implementieren. Beispielsweise können Benutzer auf den Spaltenheader klicken, um <xref:System.Windows.Controls.GridView>\-Daten gemäß den Inhalten einer bestimmten Spalte zu sortieren.  
  
> [!NOTE]
>  Die Schaltflächen\-Steuerelemente, die <xref:System.Windows.Controls.GridView> für Spaltenheader verwendet, werden von <xref:System.Windows.Controls.Primitives.ButtonBase> abgeleitet.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.GridView>\-Ansicht von <xref:System.Windows.Controls.ListView>\-Inhalt.  
  
 **GridView\-Ansicht des ListView\-Inhalts**  
  
 ![Formatierte ListView](../../../../docs/framework/wpf/controls/media/styledlistview.png "StyledListView")  
  
 <xref:System.Windows.Controls.GridView>\-Spalten werden durch <xref:System.Windows.Controls.GridViewColumn>\-Objekte dargestellt, die ihre Größe automatisch an ihren Inhalt anpassen können.  Optional können Sie explizit eine <xref:System.Windows.Controls.GridViewColumn> auf eine bestimmte Breite festlegen.  Sie können die Größe der Spalten ändern, indem Sie den Ziehpunkt zwischen Spaltenheadern ziehen.  Sie können Spalten auch dynamisch hinzufügen, entfernen, ersetzen und neu anordnen, da diese Funktionen in <xref:System.Windows.Controls.GridView> integriert sind.  <xref:System.Windows.Controls.GridView> kann jedoch die angezeigten Daten nicht direkt aktualisieren.  
  
 Im folgenden Beispiel wird gezeigt, wie eine <xref:System.Windows.Controls.GridView> definiert wird, die Mitarbeiterdaten anzeigt.  In diesem Beispiel definiert <xref:System.Windows.Controls.ListView> `EmployeeInfoDataSource` als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.  Die Eigenschaftendefinitionen von <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> binden <xref:System.Windows.Controls.GridViewColumn>\-Inhalt an `EmployeeInfoDataSource`\-Datenkategorien.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 In der folgenden Abbildung ist die im vorherigen Beispiel erstellte Tabelle dargestellt.  
  
 **GridView, die Daten von einer ItemsSource anzeigt**  
  
 ![ListView mit GridView&#45;Ausgabe](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## GridView\-Layout und \-Stil  
 Die Spaltenzellen und die Spaltenheader einer <xref:System.Windows.Controls.GridViewColumn> weisen die gleiche Breite auf.  Standardmäßig passt jede Spalte die Größe ihrer Breite an ihre Inhalte an.  Optional können Sie eine Spalte auf eine feste Breite festlegen.  
  
 Verwandte Dateninhalte werden in horizontalen Zeilen angezeigt.  In der vorherigen Abbildung werden z. B. die Nachnamen, Vornamen und ID\-Nummern der einzelnen Mitarbeiter als Gruppe angezeigt, da diese Angaben in einer horizontalen Zeile auftreten.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### Definieren und Formatieren von Spalten in einer GridView  
 Wenn Sie das Datenfeld definieren, das in einer <xref:System.Windows.Controls.GridViewColumn> angezeigt werden soll, verwenden Sie die Eigenschaft <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> oder <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A>.  Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>\-Eigenschaft hat Vorrang gegenüber beiden Vorlageneigenschaften.  
  
 Um die Ausrichtung der Spalteninhalte einer <xref:System.Windows.Controls.GridView> anzugeben, definieren Sie eine <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  Verwenden Sie nicht die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>\-Eigenschaft für <xref:System.Windows.Controls.ListView>\-Inhalte, die mit einer <xref:System.Windows.Controls.GridView> angezeigt werden.  
  
 Um Vorlage und Stileigenschaften für Spaltenheader anzugeben, verwenden Sie die Klassen <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> und <xref:System.Windows.Controls.GridViewColumnHeader>.  Weitere Informationen finden Sie unter [Übersicht über GridView\-Spaltenheaderstile und \-Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### Hinzufügen von visuellen Elementen zu einer GridView  
 Um visuelle Elemente wie das <xref:System.Windows.Controls.CheckBox>\-Steuerelement und das <xref:System.Windows.Controls.Button>\-Steuerelement einem <xref:System.Windows.Controls.GridView>\-Ansichtsmodus hinzuzufügen, verwenden Sie Vorlagen oder Stile.  
  
 Wenn Sie ein visuelles Element explizit als Datenelement definieren, kann es nur einmal in einer <xref:System.Windows.Controls.GridView> enthalten sein.  Diese Begrenzung besteht, da ein Element nur ein übergeordnetes Element haben und daher nur einmal in der [visuellen Struktur](GTMT) auftreten kann.  
  
<a name="StylingRowsinaGridViewView"></a>   
### Formatieren von Zeilen in einer GridView  
 Verwenden Sie die <xref:System.Windows.Controls.GridViewRowPresenter>\-Klasse und die <xref:System.Windows.Controls.GridViewHeaderRowPresenter>\-Klasse, um die Zeilen einer <xref:System.Windows.Controls.GridView> zu formatieren und anzuzeigen.  Ein Beispiel dafür, wie Zeilen in einem <xref:System.Windows.Controls.GridView>\-Ansichtsmodus formatiert werden, finden Sie unter [Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### Ausrichtungsprobleme beim Verwenden von ItemContainerStyle  
 Um Ausrichtungsprobleme zwischen Spaltenheadern und Zellen zu vermeiden, legen Sie keine Eigenschaft fest und geben Sie keine Vorlage an, die die Breite eines Elements in einem <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> beeinflussen kann.  Legen Sie beispielsweise die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft nicht fest, und geben Sie keine <xref:System.Windows.Controls.ControlTemplate> an, die ein <xref:System.Windows.Controls.CheckBox> einem <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> hinzufügt, der auf einem <xref:System.Windows.Controls.ListView>\-Steuerelement definiert ist.  Geben Sie stattdessen die Eigenschaften und Vorlagen an, die sich direkt auf die Spaltenbreite für Klassen auswirken, die einen <xref:System.Windows.Controls.GridView>\-Ansichtsmodus definieren.  
  
 Wenn Sie z. B. ein <xref:System.Windows.Controls.CheckBox> den Zeilen eines <xref:System.Windows.Controls.GridView>\-Ansichtsmodus hinzufügen möchten, fügen Sie das <xref:System.Windows.Controls.CheckBox> einer <xref:System.Windows.DataTemplate> hinzu, und legen Sie anschließend die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>\-Eigenschaft auf diese <xref:System.Windows.DataTemplate> fest.  
  
<a name="InteractingwithaGridViewControl"></a>   
## Benutzerinteraktionen mit einer GridView  
 Wenn Sie eine <xref:System.Windows.Controls.GridView> in Ihrer Anwendung verwenden, können Benutzer mit der Formatierung der <xref:System.Windows.Controls.GridView> interagieren und Änderungen daran vornehmen.  Beispielsweise können Benutzer die Spalten neu anordnen, die Spaltengröße ändern, Elemente in einer Tabelle auswählen und einen Bildlauf durch Inhalte durchführen.  Sie können auch einen Ereignishandler definieren, der antwortet, wenn ein Benutzer auf die Spaltenheader\-Schaltfläche klickt.  Der Ereignishandler kann Vorgänge wie das Sortieren von Daten ausführen, die gemäß den Inhalten einer Spalte in der <xref:System.Windows.Controls.GridView> angezeigt werden.  
  
 In der folgenden Liste werden die Funktionen für die Verwendung von <xref:System.Windows.Controls.GridView> für die Benutzerinteraktion im Detail erläutert:  
  
-   **Neuanordnen von Spalten mit Drag & Drop**  
  
     Benutzer können Spalten in einer <xref:System.Windows.Controls.GridView> neu anordnen, indem Sie die linke Maustaste drücken, während sich die Maus über einem Spaltenheader befindet, und anschließend die Spalte in eine neue Position ziehen.  Während der Benutzer den Spaltenheader zieht, wird eine unverankerte Version des Headers sowie eine durchgehende schwarze Linie angezeigt, die zeigt, wo die Spalte eingefügt werden soll.  
  
     Wenn Sie den Standardstil für die unverankerte Version eines Headers ändern möchten, geben Sie eine <xref:System.Windows.Controls.ControlTemplate> für einen <xref:System.Windows.Controls.GridViewColumnHeader>\-Typ an, die ausgelöst wird, wenn die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>\-Eigenschaft auf <xref:System.Windows.Controls.GridViewColumnHeaderRole> festgelegt wird.  Weitere Informationen finden Sie unter [Erstellen eines Stils für einen gezogenen GridView\-Spaltenheader](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Ändern der Größe einer Spalte gemäß ihrem Inhalt**  
  
     Benutzer können auf den Ziehpunkt rechts neben dem Spaltenheader doppelklicken, um die Größe einer Spalte gemäß ihrem Inhalt zu ändern.  
  
    > [!NOTE]
    >  Wenn Sie die <xref:System.Windows.Controls.GridViewColumn.Width%2A>\-Eigenschaft auf `Double.NaN` festlegen, erhalten Sie denselben Effekt.  
  
-   **Auswählen von Zeilenelementen**  
  
     Benutzer können ein oder mehrere Elemente in einer <xref:System.Windows.Controls.GridView> auswählen.  
  
     Informationen zum Ändern des <xref:System.Windows.Style> eines ausgewählten Elements finden Sie unter [Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Durchführen eines Bildlaufs zum Anzeigen von Inhalten, die auf dem Bildschirm anfänglich nicht sichtbar sind**  
  
     Wenn die Größe der <xref:System.Windows.Controls.GridView> nicht ausreicht, um alle Elemente anzuzeigen, können Benutzer einen horizontalen oder vertikalen Bildlauf durchführen, indem Sie die Bildlaufleisten verwenden, die von einem <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement bereitgestellt werden.  Eine <xref:System.Windows.Controls.Primitives.ScrollBar> wird ausgeblendet, wenn der ganze Inhalt in einer bestimmten Richtung sichtbar ist.  Spaltenheader führen keinen Bildlauf mit einer vertikalen, jedoch mit einer horizontalen Bildlaufleite durch.  
  
-   **Interagieren mit Spalten durch Klicken auf die Spaltenheader\-Schaltflächen**  
  
     Wenn Benutzer auf eine Spaltenheader\-Schaltfläche klicken, können sie die in der Spalte angezeigten Daten sortieren, sofern Sie einen Sortieralgorithmus bereitgestellt haben.  
  
     Sie können das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis für Spaltenheader\-Schaltflächen behandeln, um Funktionalität wie einen Sortieralgorithmus hinzuzufügen.  Um das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis für einen einzelnen Spaltenheader zu behandeln, legen Sie einen Ereignishandler auf dem <xref:System.Windows.Controls.GridViewColumnHeader> fest.  Um einen Ereignishandler festzulegen, der das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis für alle Spaltenheader behandelt, legen Sie den Handler auf dem <xref:System.Windows.Controls.ListView>\-Steuerelement fest.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## Abrufen anderer benutzerdefinierter Ansichten  
 Die <xref:System.Windows.Controls.GridView>\-Klasse, die von der abstrakten <xref:System.Windows.Controls.ViewBase>\-Klasse abgeleitet ist, ist nur einer der möglichen Ansichtsmodi für die <xref:System.Windows.Controls.ListView>\-Klasse.  Sie können andere benutzerdefinierte Ansichten für <xref:System.Windows.Controls.ListView> erstellen, indem Sie sie von der <xref:System.Windows.Controls.ViewBase>\-Klasse ableiten.  Ein Beispiel für einen benutzerdefinierten Ansichtsmodus finden Sie unter [Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## GridView\-unterstützende Klassen  
 Die folgenden Klassen unterstützen den <xref:System.Windows.Controls.GridView>\-Ansichtsmodus.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Controls.GridViewColumn>   
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.ViewBase>   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Sortieren einer GridView\-Spalte beim Klicken auf einen Header](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)