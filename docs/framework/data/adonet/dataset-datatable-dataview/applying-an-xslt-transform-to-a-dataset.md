---
title: Anwenden einer XSLT-Transformation auf ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 3f066f29b99ade6e92a263110fed8079208567b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151493"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>Anwenden einer XSLT-Transformation auf ein DataSet

Mit der **WriteXml-Methode** der <xref:System.Data.DataSet> können Sie den Inhalt eines **DataSet** als XML-Daten schreiben. Häufig werden diese XML-Daten anschließend mit XSL-Transformationen (XSLT) in ein anderes Format transformiert. Durch das Synchronisieren eines **DataSets** mit <xref:System.Xml.XmlDataDocument> einem können Sie jedoch ein XSLT-Stylesheet auf den Inhalt eines **DataSets** anwenden, ohne den Inhalt des **DataSet** zunächst als XML-Daten mit **WriteXml**schreiben zu müssen.  
  
 Im folgenden Beispiel wird ein **DataSet** mit Tabellen und Beziehungen aufgewirlegt, das **DataSet** mit einem **XmlDataDocument**synchronisiert und ein Teil des **DataSet** als HTML-Datei mithilfe eines XSLT-Stylesheets schreibt. Im Folgenden finden Sie den Inhalt des XSLT-Stylesheets:
  
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
  
 Der folgende Code füllt das **DataSet** und wendet das XSLT-Stylesheet an.  
  
> [!NOTE]
> Wenn Sie ein XSLT-Stylesheet auf ein **DataSet** anwenden, das Beziehungen enthält, erzielen <xref:System.Data.DataRelation> Sie die beste Leistung, wenn Sie die **Nested-Eigenschaft** des für jede geschachtelte Beziehung auf **true** festlegen. Dies ermöglicht Ihnen die Verwendung von XSLT-Stylesheets, die bei der Navigation in der Hierarchie und bei der Datentransformation eine Verarbeitung in natürlicher Reihenfolge von oben nach unten implementieren und bei der Navigation in der Datenhierarchie im Gegensatz zu XPath-Positionsachsen (z. B. vorausgehend-nebengeordnete und nachfolgend-nebengeordnete Elemente in Stylesheetausdrücken für Knotentsts) nicht mit Leistungseinbußen verbunden sind. Weitere Informationen zu verschachtelten Beziehungen finden Sie unter [Verschachteln von DataRelations](nesting-datarelations.md).  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [DataSet- und XmlDataDocument-Synchronisierung](dataset-and-xmldatadocument-synchronization.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
