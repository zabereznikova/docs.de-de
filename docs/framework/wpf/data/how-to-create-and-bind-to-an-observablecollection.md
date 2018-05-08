---
title: 'Gewusst wie: Erstellen und Binden an ObservableCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 5e04aa1a1d209074dbdadcb1df089e31efa84ded
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Gewusst wie: Erstellen und Binden an ObservableCollection
In diesem Beispiel wird gezeigt, wie zum Erstellen und Binden an eine Auflistung, die von abgeleitet ist die <xref:System.Collections.ObjectModel.ObservableCollection%601> Klasse, die eine Auflistungsklasse, die Benachrichtigungen bereitstellt, wenn Elemente hinzugefügt oder entfernt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Implementierung einer `NameList`-Auflistung veranschaulicht:  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 Die Auflistung wird für die Bindung auf die gleiche Weise wie bei anderen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Objekten zur Verfügung gestellt. Informationen dazu finden Sie unter [Bereitstellen von Daten für die Bindung in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md). Sie können beispielsweise die Auflistung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] instanziieren und sie als Ressource, wie hier dargestellt, angeben:  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 Danach können Sie eine Bindung an die Auflistung erstellen:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 Die Definition von `NameItemTemplate` wird hier nicht gezeigt.  
  
> [!NOTE]
>  Die Objekte in der Auflistung müssen die unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md) beschriebenen Anforderungen erfüllen. Insbesondere bei Verwendung von <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> (angenommen, Sie möchten Ihre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualisieren, wenn die Eigenschaften dynamisch ändern), müssen Sie einen Benachrichtigungsmechanismus geeignete Eigenschaft geändert wurde, z. B. die implementieren<xref:System.ComponentModel.INotifyPropertyChanged>Schnittstelle.  
  
 Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md) unter „Binden an Auflistungen“.  
  
## <a name="see-also"></a>Siehe auch  
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
