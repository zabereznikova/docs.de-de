---
title: "Anwenden einer XSLT-Transformation auf ein DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Anwenden einer XSLT-Transformation auf ein DataSet
Mit der **WriteXml**\-Methode des <xref:System.Data.DataSet> können Sie den Inhalt eines **DataSet** als XML\-Daten schreiben.  Häufig werden diese XML\-Daten anschließend mit XSL\-Transformationen \(XSLT\) in ein anderes Format umgewandelt.  Allerdings besteht durch die Synchronisierung eines **DataSet** mit einem <xref:System.Xml.XmlDataDocument> die Möglichkeit, ein XSLT\-Stylesheet auf den Inhalt eines **DataSet** anzuwenden, ohne den Inhalt des **DataSet** mit **WriteXml** zunächst als XML\-Daten schreiben zu müssen.  
  
 Im folgenden Beispiel wird ein **DataSet** mit Tabellen und Beziehungen gefüllt. Anschließend wird das **DataSet** mit einem **XmlDataDocument** synchronisiert, und ein Teil des **DataSet** wird mithilfe eines XSLT\-Stylesheets als HTML\-Datei geschrieben.  Ein XSLT\-Stylesheet hat folgenden Inhalt:  
  
```  
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
  
 Mit dem folgenden Code wird das **DataSet** gefüllt, und das XSLT\-Stylesheet wird angewendet.  
  
> [!NOTE]
>  Wenn das **DataSet**, auf das Sie ein XSLT\-Stylesheet anwenden, Beziehungen enthält, erreichen Sie die größtmögliche Leistung, indem Sie die **Nested**\-Eigenschaft der <xref:System.Data.DataRelation> für jede geschachtelte Beziehung auf **true** festlegen.  Dies ermöglicht Ihnen die Verwendung von XSLT\-Stylesheets, die bei der Navigation in der Hierarchie und bei der Datentransformation eine Verarbeitung in natürlicher Reihenfolge von oben nach unten implementieren und bei der Navigation in der Datenhierarchie im Gegensatz zu XPath\-Positionsachsen \(z. B. vorausgehend\-nebengeordnete und nachfolgend\-nebengeordnete Elemente in Stylesheetausdrücken für Knotentsts\) nicht mit Leistungseinbußen verbunden sind.  Weitere Informationen finden Sie unter [Schachteln von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
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
  
## Siehe auch  
 [Synchronisierung zwischen 'DataSet' und 'XmlDataDocument'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)