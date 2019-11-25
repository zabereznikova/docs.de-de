---
title: 'How to: Join Two Collections (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
ms.openlocfilehash: 404a43f52fce141b515da389090c81c57186f2e2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344534"
---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a>How to: Join Two Collections (LINQ to XML) (Visual Basic)
Ein Element oder Attribut in einem XML-Dokument kann mitunter auf ein anderes Element oder Attribut verweisen. So enthält das XML-Dokument in [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) z.B. eine Liste von Kunden und eine Liste von Aufträgen. Jedes `Customer`-Element enthält ein `CustomerID`-Attribut. Jedes `Order`-Element enthält ein `CustomerID`-Element. Das `CustomerID`-Element eines Auftrags verweist auf das `CustomerID`-Attribut eines Kunden.  
  
 Das Thema [Beispiel-XSD-Datei: Kunden und Bestellungen](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) enthält ein XSD-Schema, das zum Validieren dieses Dokuments verwendet werden kann. Mit den Funktionen `xs:key` und `xs:keyref` des XSD-Schemas wird geprüft, ob das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist. Außerdem wird damit eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element hergestellt.  
  
 Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie diese Beziehung durch Verwenden der `Join`-Klausel nutzen.  
  
 Da es keinen Index gibt, führt eine solche Verknüpfung zu einer schlechten Laufzeitleistung.  
  
 For more detailed information about `Join`, see [Join Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verknüpft die `Customer`-Elemente mit den `Order`-Elementen und generiert ein neues XML-Dokument, das das `CompanyName`-Element der Aufträge enthält.  
  
 Vor dem Ausführen der Abfrage überprüft das Beispiel, ob das Dokument dem Schema in [Beispiel-XSD-Datei: Kunden und Bestellungen](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) entspricht. Auf diese Weise wird sichergestellt, dass die JOIN-Klausel immer funktioniert.  
  
 Diese Abfrage ruft zuerst alle `Customer`-Elemente ab und verknüpft sie dann mit den `Order`-Elementen. Sie wählt dabei nur die Aufträge der Kunden aus, deren `CustomerID` größer als "K" ist. Anschließend projiziert die Abfrage ein neues `Order`-Element, das die Kundeninformationen in den einzelnen Aufträgen enthält.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
 In diesem Beispiel wird das folgende XML-Schema verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).  
  
 Beachten Sie, dass diese Art von Verknüpfungen zu Leistungseinbußen führt. Joins (Verknüpfungen) werden über eine lineare Suche ausgeführt. Es gibt keine Hashtabellen oder Indizes, die die Geschwindigkeit erhöhen könnten.  
  
```vb  
Public Class Program  
    Public Shared errors As Boolean = False  
  
    Public Shared Function LamValidEvent(ByVal o As Object, _  
                 ByVal e As ValidationEventArgs) As Boolean  
        Console.WriteLine("{0}", e.Message)  
        errors = True  
    End Function  
  
    Shared Sub Main()  
        Dim schemas As New XmlSchemaSet()  
        schemas.Add("", "CustomersOrders.xsd")  
  
        Console.Write("Attempting to validate, ")  
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
  
        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))  
        If errors Then  
            Console.WriteLine("custOrdDoc did not validate")  
        Else  
            Console.WriteLine("custOrdDoc validated")  
        End If  
  
        If Not errors Then  
            'Join customers and orders, and create a new XML document with  
            ' a different shape.  
            'The new document contains orders only for customers with a  
            ' CustomerID > 'K'.  
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault  
            Dim newCustOrd As XElement = _  
                <Root>  
                    <%= From c In custOrd.<Customers>.<Customer> _  
                        Join o In custOrd.<Orders>.<Order> _  
                        On c.@CustomerID Equals o.<CustomerID>.Value _  
                        Where c.@CustomerID.CompareTo("K") > 0 _  
                        Select _  
                        <Order>  
                            <CustomerID><%= c.@CustomerID %></CustomerID>  
                            <%= c.<CompanyName> %>  
                            <%= c.<ContactName> %>  
                            <%= o.<EmployeeID> %>  
                            <%= o.<OrderDate> %>  
                        </Order> _  
                    %>  
                </Root>  
            Console.WriteLine(newCustOrd)  
        End If  
    End Sub  
End Class  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console
Attempting to validate, custOrdDoc validated  
<Root>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-03-21T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-05-22T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-06-25T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-10-27T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>6</EmployeeID>  
    <OrderDate>1997-11-10T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>4</EmployeeID>  
    <OrderDate>1998-02-12T00:00:00</OrderDate>  
  </Order>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Advanced Query Techniques (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
