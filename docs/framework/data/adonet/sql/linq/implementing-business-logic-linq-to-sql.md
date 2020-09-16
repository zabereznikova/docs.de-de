---
title: Implementieren von Geschäftslogik (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: a8be0bd542c76e732d47c19f1d3b578884e2b5ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558926"
---
# <a name="implementing-business-logic-linq-to-sql"></a>Implementieren von Geschäftslogik (LINQ to SQL)
Der Begriff "Geschäftslogik" bezieht sich in diesem Thema auf benutzerdefinierte Regeln oder Validierungstests, die auf Daten angewendet werden, bevor diese eingefügt, aktualisiert oder aus der Datenbank gelöscht werden. Der Begriff Geschäftslogik wird zeitweise synonym mit "Geschäftsregeln" oder "Domänenlogik" verwendet. In N-Tier-Anwendungen wird Geschäftslogik normalerweise als logische Ebene bezeichnet, die somit unabhängig von der Präsentationsebene oder Datenzugriffsebene geändert werden kann. Die Geschäftslogik kann von der Datenzugriffsebene aufgerufen werden, bevor oder nachdem Daten in der Datenbank aktualisiert, eingefügt oder gelöscht werden.  
  
 Mit der Geschäftslogik kann genauso einfach wie anhand einer Schemavalidierung festgestellt werden, ob der Typ des Feldes mit dem Typ der Tabellenspalte kompatibel ist. Alternativ kann sie aus einem Satz von Objekten bestehen, die auf beliebig komplexe Weisen interagieren. Die Regeln werden möglicherweise als gespeicherte Prozeduren in der Datenbank oder als Objekte im Arbeitsspeicher implementiert. Wenn die Geschäftslogik jedoch implementiert ist, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ermöglicht es Ihnen, partielle Klassen und partielle Methoden zu verwenden, um die Geschäftslogik vom Datenzugriffs Code zu trennen.  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a>Aufrufen der Geschäftslogik durch LINQ to SQL  
 Wenn Sie zur Entwurfszeit eine Entitäts Klasse generieren, entweder manuell oder mithilfe des objektrelationaler Designer oder SQLMetal, wird Sie als partielle Klasse definiert. Dies bedeutet, dass Sie in einer separaten Codedatei einen anderen Teil der Entitätsklasse festlegen können, in der die benutzerdefinierte Geschäftslogik enthalten ist. Zur Kompilierungszeit werden die beiden Teile in eine einzelne Klasse zusammengeführt. Wenn Sie jedoch die Entitäts Klassen mithilfe der objektrelationaler Designer oder SQLMetal neu generieren müssen, können Sie dies tun, und Ihr Teil der Klasse wird nicht geändert.  
  
 Die partiellen Klassen, durch die Entitäten definiert werden, und <xref:System.Data.Linq.DataContext> enthalten partielle Methoden. Dabei handelt es sich um Erweiterungspunkte, über die Sie die Geschäftslogik anwenden können, bevor und nachdem Sie Updates, Einfügungen oder Löschungen für eine Entität oder Entitätseigenschaft ausführen. Partielle Methoden können als Kompilierzeitereignisse betrachtet werden. Der Code-Generator definiert eine Methodensignatur und ruft die Methoden in den get- und set-Eigenschaftenaccessoren, im `DataContext`-Konstruktor und in einigen Fällen im Hintergrund auf, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird. Wenn Sie jedoch keine bestimmte partielle Methode implementieren, werden alle darauf gerichteten Verweise sowie die Definition während der Kompilierung entfernt.  
  
 In der Implementierungsdefinition, die Sie in eine separate Codedatei schreiben, können Sie beliebige benutzerdefinierte Logik aufnehmen. Sie können die partielle Klasse selbst als Domänenebene verwenden oder einen Aufruf von der Implementierungsdefinition der partiellen Methode in separate Objekte ausführen. Die Geschäftslogik wird auf beide Weisen klar sowohl vom Datenzugriffscode als auch vom Präsentationsebenencode getrennt.  
  
## <a name="a-closer-look-at-the-extensibility-points"></a>Genauere Betrachtung der Erweiterungspunkte  
 Das folgende Beispiel zeigt einen Teil des Codes, der vom-objektrelationaler Designer für die `DataContext` -Klasse generiert wurde, die über zwei Tabellen verfügt: `Customers` und `Orders` . Beachten Sie, dass Einfüge-, Update- und Löschmethoden für jede Tabelle in der Klasse definiert werden.  
  
```vb  
Partial Public Class Northwnd  
    Inherits System.Data.Linq.DataContext  
  
    Private Shared mappingSource As _  
        System.Data.Linq.Mapping.MappingSource = New _  
        AttributeMappingSource  
  
    #Region "Extensibility Method Definitions"  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub InsertCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub UpdateCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub DeleteCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub InsertOrder(instance As [Order])  
    End Sub  
    Partial Private Sub UpdateOrder(instance As [Order])  
    End Sub  
    Partial Private Sub DeleteOrder(instance As [Order])  
    End Sub  
    #End Region  
```  
  
```csharp  
public partial class MyNorthWindDataContext : System.Data.Linq.DataContext  
    {  
        private static System.Data.Linq.Mapping.MappingSource mappingSource = new AttributeMappingSource();  
  
        #region Extensibility Method Definitions  
        partial void OnCreated();  
        partial void InsertCustomer(Customer instance);  
        partial void UpdateCustomer(Customer instance);  
        partial void DeleteCustomer(Customer instance);  
        partial void InsertOrder(Order instance);  
        partial void UpdateOrder(Order instance);  
        partial void DeleteOrder(Order instance);  
        #endregion  
```  
  
 Wenn Sie die Einfüge-, Update- und Löschmethoden in Ihrer partiellen Klasse implementieren, werden sie von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit anstelle ihrer eigenen Standardmethoden aufgerufen, sobald <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen wird. Auf diese Weise können Sie das Standardverhalten für Erstellungs-, Lese-, Update- und Löschoperationen überschreiben. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anpassen des Einfüge-, Aktualisierungs-und Lösch Verhaltens von Entitäts Klassen](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).  
  
 Die `OnCreated`-Methode wird im Klassenkonstruktor aufgerufen.  
  
```vb  
Public Sub New(ByVal connection As String)  
    MyBase.New(connection, mappingSource)  
    OnCreated()  
End Sub  
```  
  
```csharp  
public MyNorthWindDataContext(string connection) :  
            base(connection, mappingSource)  
        {  
            OnCreated();  
        }  
```  
  
 Die Entitätsklassen verfügen über drei Methoden, die von der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Laufzeit aufgerufen werden, wenn die Entität (beim Aufrufen von `SubmitChanges`) erstellt, geladen und überprüft wird. Die Entitätsklassen verfügen außerdem über zwei partielle Methoden für jede Eigenschaft, eine davon wird vor dem Festlegen der Eigenschaft und die andere danach aufgerufen. Im folgenden Codebeispiel werden einige der für die `Customer`-Klasse generierten Methoden veranschaulicht:  
  
```vb  
#Region "Extensibility Method Definitions"  
    Partial Private Sub OnLoaded()  
    End Sub  
    Partial Private Sub OnValidate(action As _  
        System.Data.Linq.ChangeAction)  
    End Sub  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub OnCustomerIDChanging(value As String)  
    End Sub  
    Partial Private Sub OnCustomerIDChanged()  
    End Sub  
    Partial Private Sub OnCompanyNameChanging(value As String)  
    End Sub  
    Partial Private Sub OnCompanyNameChanged()  
    End Sub  
' ...Additional Changing/Changed methods for each property.  
```  
  
```csharp  
#region Extensibility Method Definitions  
    partial void OnLoaded();  
    partial void OnValidate();  
    partial void OnCreated();  
    partial void OnCustomerIDChanging(string value);  
    partial void OnCustomerIDChanged();  
    partial void OnCompanyNameChanging(string value);  
    partial void OnCompanyNameChanged();  
// ...additional Changing/Changed methods for each property  
```  
  
 Die Methoden werden im set-Accessor der Eigenschaft aufgerufen, wie im folgenden Beispiel für die `CustomerID`-Eigenschaft veranschaulicht:  
  
```vb  
Public Property CustomerID() As String  
    Set  
        If (String.Equals(Me._CustomerID, value) = False) Then  
            Me.OnCustomerIDChanging(value)  
            Me.SendPropertyChanging()  
            Me._CustomerID = value  
            Me.SendPropertyChanged("CustomerID")  
            Me.OnCustomerIDChanged()  
        End If  
    End Set  
End Property  
```  
  
```csharp  
public string CustomerID  
{  
    set  
    {  
        if ((this._CustomerID != value))  
        {  
            this.OnCustomerIDChanging(value);  
            this.SendPropertyChanging();  
            this._CustomerID = value;  
            this.SendPropertyChanged("CustomerID");  
            this.OnCustomerIDChanged();  
        }  
     }  
}  
```  
  
 In Ihren Teil der Klasse schreiben Sie eine Implementierungsdefinition der Methode. In Visual Studio `partial` wird IntelliSense für die Methoden Definitionen im anderen Teil der Klasse angezeigt, nachdem Sie Sie eingeben.  
  
```vb  
Partial Public Class Customer  
    Private Sub OnCustomerIDChanging(value As String)  
        ' Perform custom validation logic here.  
    End Sub  
End Class  
```  
  
```csharp  
partial class Customer
    {  
        partial void OnCustomerIDChanging(string value)  
        {  
            //Perform custom validation logic here.  
        }  
    }  
```  
  
 Weitere Informationen darüber, wie Sie Ihrer Anwendung mithilfe von partiellen Methoden Geschäftslogik hinzufügen, finden Sie in den folgenden Themen:  
  
 [Gewusst wie: Hinzufügen von Validierungen zu Entitätsklassen](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [Exemplarische Vorgehensweise: Anpassen des Einfüge-, Update- und Löschverhaltens in Entitätsklassen](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [Exemplarische Vorgehensweise: Hinzufügen einer Validierung zu Entitätsklassen](/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))  
  
## <a name="see-also"></a>Siehe auch

- [Partielle Klassen und Methoden](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [Partielle Methoden](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
