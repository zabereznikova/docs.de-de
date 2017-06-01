---
title: "Gewusst wie: Sortieren einer GridView-Spalte beim Klicken auf einen Header | Microsoft Docs"
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
  - "GridView-Steuerelemente"
  - "ListView-Steuerelemente"
  - "ListView-Steuerelemente, Sortieren von GridView-Spalten"
  - "GridView-Steuerelemente, ListView-Steuerelement"
ms.assetid: 4865d720-d147-40ed-83a7-af7587f8aad8
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Sortieren einer GridView-Spalte beim Klicken auf einen Header
In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView> anzeigen, Modus und sortiert die Daten zu Inhalten, wenn ein Benutzer auf einen Spaltenheader klickt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Controls.GridView> mit drei Spalten, die zum Binden der <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, und <xref:System.DateTime.Day%2A>, Eigenschaften der <xref:System.DateTime> Struktur.  
  
```xaml  
<GridView>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Year}"   
                  Header="Year"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Month}"   
                  Header="Month"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Day}"   
                  Header="Day"  
                  Width="100"/>  
</GridView>  
```  
  
 Das folgende Beispiel zeigt die Datenelemente, die sich aus einer <xref:System.Collections.ArrayList> von <xref:System.DateTime> Objekte. Die <xref:System.Collections.ArrayList> ist definiert als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.ListView> Steuerelement.  
  
```xaml  
<ListView.ItemsSource>  
  <s:ArrayList>  
    <p:DateTime>1993/1/1 12:22:02</p:DateTime>  
    <p:DateTime>1993/1/2 13:2:01</p:DateTime>  
    <p:DateTime>1997/1/3 2:1:6</p:DateTime>  
    <p:DateTime>1997/1/4 13:6:55</p:DateTime>  
    <p:DateTime>1999/2/1 12:22:02</p:DateTime>  
    <p:DateTime>1998/2/2 13:2:01</p:DateTime>  
    <p:DateTime>2000/2/3 2:1:6</p:DateTime>  
    <p:DateTime>2002/2/4 13:6:55</p:DateTime>  
    <p:DateTime>2001/3/1 12:22:02</p:DateTime>  
    <p:DateTime>2006/3/2 13:2:01</p:DateTime>  
    <p:DateTime>2004/3/3 2:1:6</p:DateTime>  
    <p:DateTime>2004/3/4 13:6:55</p:DateTime>  
  </s:ArrayList>  
</ListView.ItemsSource>  
```  
  
 Die `s` und `p` Bezeichner in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Tags finden Sie unter Namespacezuordnungen, die in den Metadaten definiert sind die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite. Das folgende Beispiel zeigt die Metadatendefinition.  
  
```xaml  
<Window        
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Class="ListViewSort.Window1"      
    xmlns:s="clr-namespace:System.Collections;assembly=mscorlib"  
    xmlns:p="clr-namespace:System;assembly=mscorlib">  
```  
  
 Um die Daten gemäß den Inhalt einer Spalte zu sortieren, definiert das Beispiel einen Ereignishandler zur Behandlung der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis tritt auf, wenn Sie die Spaltenheader-Schaltfläche drücken. Das folgende Beispiel zeigt, wie einen Ereignishandler für das <xref:System.Windows.Controls.GridViewColumnHeader> Steuerelement.  
  
```xaml  
<ListView x:Name='lv' Height="150" HorizontalAlignment="Center"   
  VerticalAlignment="Center"   
  GridViewColumnHeader.Click="GridViewColumnHeaderClickedHandler"  
 >  
```  
  
 Das Beispiel definiert den Ereignishandler, um die Sortierreihenfolge zu ändern, zwischen aufsteigend und absteigend Sie jedes Mal aus, die die Spaltenheader-Schaltfläche drücken. Im folgende Beispiel wird der Ereignishandler veranschaulicht.  
  
```csharp  
public partial class Window1 : Window  
{  
    public Window1()  
    {  
        InitializeComponent();  
    }  
  
    GridViewColumnHeader _lastHeaderClicked = null;  
    ListSortDirection _lastDirection = ListSortDirection.Ascending;  
  
    void GridViewColumnHeaderClickedHandler(object sender,  
                                            RoutedEventArgs e)  
    {  
        GridViewColumnHeader headerClicked =  
              e.OriginalSource as GridViewColumnHeader;  
        ListSortDirection direction;  
  
        if (headerClicked != null)  
        {  
            if (headerClicked.Role != GridViewColumnHeaderRole.Padding)  
            {  
                if (headerClicked != _lastHeaderClicked)  
                {  
                    direction = ListSortDirection.Ascending;  
                }  
                else  
                {  
                    if (_lastDirection == ListSortDirection.Ascending)  
                    {  
                        direction = ListSortDirection.Descending;  
                    }  
                    else  
                    {  
                        direction = ListSortDirection.Ascending;  
                    }  
                }  
  
                string header = headerClicked.Column.Header as string;  
                Sort(header, direction);  
  
                if (direction == ListSortDirection.Ascending)  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowUp"] as DataTemplate;  
                }  
                else  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowDown"] as DataTemplate;  
                }  
  
                // Remove arrow from previously sorted header  
                if (_lastHeaderClicked != null && _lastHeaderClicked != headerClicked)  
                {  
                    _lastHeaderClicked.Column.HeaderTemplate = null;  
                }  
  
                _lastHeaderClicked = headerClicked;  
                _lastDirection = direction;  
            }  
        }  
    }  
```  
  
```vb  
Partial Public Class Window1  
        Inherits Window  
        Public Sub New()  
            InitializeComponent()  
        End Sub  
  
        Private _lastHeaderClicked As GridViewColumnHeader = Nothing  
        Private _lastDirection As ListSortDirection = ListSortDirection.Ascending  
  
        Private Sub GridViewColumnHeaderClickedHandler(ByVal sender As Object, ByVal e As RoutedEventArgs)  
            Dim headerClicked As GridViewColumnHeader = TryCast(e.OriginalSource, GridViewColumnHeader)  
            Dim direction As ListSortDirection  
  
            If headerClicked IsNot Nothing Then  
                If headerClicked.Role <> GridViewColumnHeaderRole.Padding Then  
                    If headerClicked IsNot _lastHeaderClicked Then  
                        direction = ListSortDirection.Ascending  
                    Else  
                        If _lastDirection = ListSortDirection.Ascending Then  
                            direction = ListSortDirection.Descending  
                        Else  
                            direction = ListSortDirection.Ascending  
                        End If  
                    End If  
  
                    Dim header As String = TryCast(headerClicked.Column.Header, String)  
                    Sort(header, direction)  
  
                    If direction = ListSortDirection.Ascending Then  
                        headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowUp"), DataTemplate)  
                    Else  
                        headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowDown"), DataTemplate)  
                    End If  
  
                    ' Remove arrow from previously sorted header  
                    If _lastHeaderClicked IsNot Nothing AndAlso _lastHeaderClicked IsNot headerClicked Then  
                        _lastHeaderClicked.Column.HeaderTemplate = Nothing  
                    End If  
  
                    _lastHeaderClicked = headerClicked  
                    _lastDirection = direction  
                End If  
            End If  
        End Sub  
```  
  
 Das folgende Beispiel zeigt die sortieren-Algorithmus, der vom Ereignishandler zum Sortieren der Daten aufgerufen wird. Die Sortierung erfolgt durch Erstellen eines neuen <xref:System.ComponentModel.SortDescription> Struktur.  
  
```csharp  
private void Sort(string sortBy, ListSortDirection direction)  
{  
    ICollectionView dataView =  
      CollectionViewSource.GetDefaultView(lv.ItemsSource);  
  
    dataView.SortDescriptions.Clear();  
    SortDescription sd = new SortDescription(sortBy, direction);  
    dataView.SortDescriptions.Add(sd);  
    dataView.Refresh();  
}  
  
```  
  
```vb  
Private Sub Sort(ByVal sortBy As String, ByVal direction As ListSortDirection)  
            Dim dataView As ICollectionView = CollectionViewSource.GetDefaultView(lv.ItemsSource)  
  
            dataView.SortDescriptions.Clear()  
            Dim sd As New SortDescription(sortBy, direction)  
            dataView.SortDescriptions.Add(sd)  
            dataView.Refresh()  
        End Sub  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)