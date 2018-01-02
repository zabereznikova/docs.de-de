---
title: Anwenden einer XSLT-Transformation auf ein DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 35251c5e2a713463510b3ff8b65e9096385c6bcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="10685-102">Anwenden einer XSLT-Transformation auf ein DataSet</span><span class="sxs-lookup"><span data-stu-id="10685-102">Applying an XSLT Transform to a DataSet</span></span>
<span data-ttu-id="10685-103">Die **WriteXml** Methode der <xref:System.Data.DataSet> ermöglicht es Ihnen, den Inhalt der Schreiben einer **DataSet** als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="10685-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="10685-104">Häufig werden diese XML-Daten anschließend mit XSL-Transformationen (XSLT) in ein anderes Format transformiert.</span><span class="sxs-lookup"><span data-stu-id="10685-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="10685-105">Allerdings synchronisieren eine **DataSet** mit ein <xref:System.Xml.XmlDataDocument> ermöglicht es Ihnen, ein XSLT-Stylesheet auf den Inhalt der Anwenden einer **DataSet** ohne den Inhalt der ersten schreiben zu müssen die  **DataSet** als XML-Daten mit **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="10685-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="10685-106">Im folgenden Beispiel wird eine **DataSet** synchronisiert mit Tabellen und Beziehungen, die **DataSet** mit einer **XmlDataDocument**, und schreibt einen Teil der  **DataSet** als HTML-Datei mithilfe eines XSLT-Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="10685-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="10685-107">Ein XSLT-Stylesheet hat folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="10685-107">Following are the contents of the XSLT stylesheet.</span></span>  
  
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
  
 <span data-ttu-id="10685-108">Der folgende code füllt das **DataSet** und wendet die XSLT-Stylesheet.</span><span class="sxs-lookup"><span data-stu-id="10685-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10685-109">Wenn Sie eine XSLT-Stylesheet anwenden eine **DataSet** , Beziehungen enthält, die optimale Leistung zu erzielen, wenn Sie festlegen, die **Nested** Eigenschaft der <xref:System.Data.DataRelation> zu **"true"**für jede geschachtelte Beziehung.</span><span class="sxs-lookup"><span data-stu-id="10685-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="10685-110">Dies ermöglicht Ihnen die Verwendung von XSLT-Stylesheets, die bei der Navigation in der Hierarchie und bei der Datentransformation eine Verarbeitung in natürlicher Reihenfolge von oben nach unten implementieren und bei der Navigation in der Datenhierarchie im Gegensatz zu XPath-Positionsachsen (z. B. vorausgehend-nebengeordnete und nachfolgend-nebengeordnete Elemente in Stylesheetausdrücken für Knotentsts) nicht mit Leistungseinbußen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="10685-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="10685-111">Weitere Informationen zu geschachtelten Beziehungen, finden Sie unter [Schachteln von "DataRelations"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="10685-111">For more information on nested relations, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10685-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10685-112">See Also</span></span>  
 [<span data-ttu-id="10685-113">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="10685-113">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="10685-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="10685-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
