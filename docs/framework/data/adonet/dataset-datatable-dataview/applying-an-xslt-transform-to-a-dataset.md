---
title: Anwenden einer XSLT-Transformation auf ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 5b3aca6a71f88762084934d0d9c7cea15b5366c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034462"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>Anwenden einer XSLT-Transformation auf ein DataSet
Die **WriteXml** Methode der <xref:System.Data.DataSet> ermöglicht es Ihnen, den Inhalt des schreiben eine **DataSet** als XML-Daten. Häufig werden diese XML-Daten anschließend mit XSL-Transformationen (XSLT) in ein anderes Format transformiert. Allerdings synchronisieren ein **DataSet** mit ein <xref:System.Xml.XmlDataDocument> können Sie ein XSLT-Stylesheet auf den Inhalt Anwenden einer **DataSet** ohne zuerst den Inhalt der schreiben zu müssen die  **DataSet** als XML-Daten mit **WriteXml**.  
  
 Das folgende Beispiel füllt ein **DataSet** mit Tabellen und Beziehungen, synchronisiert der **DataSet** mit einer **XmlDataDocument**, und schreibt einen Teil der  **DataSet** als HTML-Datei mithilfe einer XSLT-Stylesheets. Ein XSLT-Stylesheet hat folgenden Inhalt:  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 Der folgende code füllt die **DataSet** und wendet das XSLT-Stylesheet.  
  
> [!NOTE]
>  Wenn Sie eine XSLT-Stylesheet anwenden einer **DataSet** , Beziehungen enthält, die Sie eine optimale Leistung erzielen, setzen Sie die **geschachtelte** Eigenschaft der <xref:System.Data.DataRelation> zu **"true"** für jede geschachtelte Beziehung. Dies ermöglicht Ihnen die Verwendung von XSLT-Stylesheets, die bei der Navigation in der Hierarchie und bei der Datentransformation eine Verarbeitung in natürlicher Reihenfolge von oben nach unten implementieren und bei der Navigation in der Datenhierarchie im Gegensatz zu XPath-Positionsachsen (z. B. vorausgehend-nebengeordnete und nachfolgend-nebengeordnete Elemente in Stylesheetausdrücken für Knotentsts) nicht mit Leistungseinbußen verbunden sind. Weitere Informationen zu geschachtelten Beziehungen, finden Sie unter [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a>Siehe auch

- [DataSet- und XmlDataDocument-Synchronisierung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
