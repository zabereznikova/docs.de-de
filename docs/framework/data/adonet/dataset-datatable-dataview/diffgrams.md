---
title: "DiffGrams | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DiffGrams
Ein DiffGram ist ein XML\-Format, das aktuelle und ursprüngliche Versionen von Datenelementen angibt.  <xref:System.Data.DataSet> verwendet das DiffGram\-Format, um seinen Inhalt zu laden und beizubehalten und um seinen Inhalt für die Übertragung über eine Netzwerkverbindung zu serialisieren.  Wenn ein <xref:System.Data.DataSet> als DiffGram geschrieben wird, füllt es das DiffGram mit allen erforderlichen Informationen zum genauen Wiederherstellen des Inhalts \(jedoch nicht des Schemas\) von <xref:System.Data.DataSet> mit den Spaltenwerten aus der **Original**\-Zeilenversion und der **Current**\-Zeilenversion sowie mit Zeilenfehlerinformationen und Zeilenreihenfolgen.  
  
 Beim Senden und Abrufen eines <xref:System.Data.DataSet> über einen XML\-Webdienst wird das DiffGram\-Format implizit verwendet.  Außerdem können Sie beim Laden des Inhalts eines <xref:System.Data.DataSet> aus XML mithilfe der **ReadXml**\-Methode oder beim Schreiben des Inhalts eines <xref:System.Data.DataSet> in XML mithilfe der **WriteXml**\-Methode festlegen, dass der Inhalt als DiffGram gelesen bzw. geschrieben werden soll.  Weitere Informationen finden Sie unter [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Schreiben von 'DataSet'\-Inhalt als XML\-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Während das DiffGram\-Format von .NET Framework primär als Serialisierungsformat für den Inhalt eines <xref:System.Data.DataSet> verwendet wird, können Sie mithilfe von DiffGrams auch Daten in Tabellen einer Microsoft SQL Server\-Datenbank ändern.  
  
 Ein Diffgram wird generiert, indem der Inhalt aller Tabellen in ein **\<diffgram\>**\-Element geschrieben wird.  
  
### So generieren Sie ein Diffgram  
  
1.  Generieren Sie eine Liste von Stammtabellen \(also Tabellen ohne irgendein übergeordnetes Element\).  
  
2.  Geben Sie im ersten Diffgram\-Abschnitt für jede Tabelle und ihre untergeordneten Tabellen in der Liste die aktuelle Version der einzelnen Zeilen an.  
  
3.  Geben Sie im Diffgram\-Abschnitt **\<before\>** für jede Tabelle im <xref:System.Data.DataSet> die Originalversion der einzelnen Zeilen an, sofern vorhanden.  
  
4.  Geben Sie im Diffgram\-Abschnitt **\<errors\>** für Zeilen mit Fehlermeldungen den Text der Fehlermeldung an.  
  
 Ein Diffgram wird vom Anfang der XML\-Datei bis zu deren Ende verarbeitet.  
  
### So verarbeiten Sie ein Diffgram  
  
1.  Verarbeiten Sie den ersten Abschnitt des Diffgram, der die aktuelle Version der Zeilen enthält.  
  
2.  Verarbeiten Sie den zweiten Abschnitt **\<before\>**, der die Originalversion der bearbeiteten und gelöschten Zeilen enthält.  
  
    > [!NOTE]
    >  Wenn eine Zeile als gelöscht gekennzeichnet ist, kann je nach der `Cascade`\-Eigenschaft des aktuellen <xref:System.Data.DataSet> der Löschvorgang auch die untergeordneten Zeilen der Zeile löschen.  
  
3.  Verarbeiten Sie den Abschnitt **\<errors\>**.  Legen Sie in diesem Abschnitt die Fehlerinformationen für die angegebene Zeile und Spalte für jedes Element fest.  
  
> [!NOTE]
>  Wenn Sie für <xref:System.Data.XmlWriteMode> "Diffgram" festlegen, kann es passieren, dass sich der Inhalt des Ziel\-<xref:System.Data.DataSet> und des Original\-<xref:System.Data.DataSet> voneinander unterscheiden.  
  
## DiffGram\-Format  
 Das DiffGram\-Format ist in drei Abschnitte unterteilt: die aktuellen Daten, die ursprünglichen \(oder "vorher"\) Daten und ein Fehlerabschnitt, wie im folgenden Beispiel dargestellt.  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Das DiffGram\-Format umfasst die folgenden Datenblöcke:  
  
 **\<**  ***DataInstance***  **\>**  
 Der Name dieses Elements, ***DataInstance***, wird in dieser Dokumentation zu Erklärungszwecken verwendet.  Ein ***DataInstance***\-Element stellt ein <xref:System.Data.DataSet> oder eine Zeile in einer <xref:System.Data.DataTable> dar.  Anstelle von *DataInstance* enthält das Element den Namen des jeweiligen <xref:System.Data.DataSet> oder der entsprechenden<xref:System.Data.DataTable>.  Dieser Block des DiffGram\-Formats enthält die aktuellen Daten, wobei es keine Rolle spielt, ob diese ggf. geändert wurden.  Ein Element oder eine Zeile, das bzw. die geändert wurde, wird mit der **diffgr:hasChanges**\-Anmerkung angegeben.  
  
 **\<diffgr:before\>**  
 Dieser Block des DiffGram\-Formats enthält die ursprüngliche Version einer Zeile.  Elemente in diesem Block werden mit Elementen im ***DataInstance***\-Block über die **diffgr:id**\-Anmerkung verglichen.  
  
 **\<diffgr:errors\>**  
 Dieser Block des DiffGram\-Formats enthält Fehlerinformationen für eine bestimmte Zeile im ***DataInstance***\-Block.  Elemente in diesem Block werden mit Elementen im ***DataInstance***\-Block über die **diffgr:id**\-Anmerkung verglichen.  
  
## DiffGram\-Anmerkungen  
 In DiffGrams wird eine Reihe von Anmerkungen verwendet, um auf Elemente aus den verschiedenen DiffGram\-Blöcken Bezug zu nehmen, die unterschiedliche Zeilenversionen oder Fehlerinformationen im <xref:System.Data.DataSet> darstellen.  
  
 In der folgenden Tabelle werden die DiffGram\-Anmerkungen beschrieben, die im DiffGram\-Namespace **urn:schemas\-microsoft\-com:xml\-diffgram\-v1** definiert sind.  
  
|Anmerkung|Beschreibung|  
|---------------|------------------|  
|**id**|Wird verwendet, um Paare aus den Elementen im **\<diffgr:before\>**\-Block und im **\<diffgr:errors\>**\-Block und den Elementen im **\<** ***DataInstance*** **\>**\-Block zu bilden.  Werte mit der **diffgr:id**\-Anmerkung haben das Format *\[Tabellenname\]\[Zeilenbezeichner\]*.  Beispiel: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Gibt an, welches Element aus dem **\<** ***DataInstance*** **\>**\-Block das übergeordnete Element des aktuellen Elements ist.  Werte mit der **diffgr:parentId**\-Anmerkung haben das Format *\[Tabellenname\]\[Zeilenbezeichner\]*.  Beispiel: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Weist eine Zeile im **\<** ***DataInstance*** **\>**\-Block als geändert aus.  Die **hasChanges**\-Anmerkung kann einen der folgenden Werte aufweisen:<br /><br /> **inserted**<br /> Gibt eine **Added**\-Zeile an.<br /><br /> **modified**<br /> Gibt eine **Modified**\-Zeile an, die eine **Original**\-Zeilenversion im **\<diffgr:before\>**\-Block enthält.  Beachten Sie, dass **Deleted**\-Zeilen über eine **Original**\-Zeilenversion im **\<diffgr:before\>**\-Block verfügen, dass jedoch im **\<** ***DataInstance*** **\>**\-Block kein Element mit Anmerkungen vorhanden ist.|  
|**hasErrors**|Gibt eine Zeile im **\<** ***DataInstance*** **\>**\-Block mit einem **RowError** an.  Das Fehlerelement wird im **\<diffgr:errors\>**\-Block positioniert.|  
|**Fehler**|Enthält den Text des **RowError** für ein bestimmtes Element im **\<diffgr:errors\>**\-Block.|  
  
 Das <xref:System.Data.DataSet> enthält weitere Anmerkungen, wenn sein Inhalt als DiffGram gelesen oder geschrieben wird.  In der folgenden Tabelle werden diese zusätzlichen Anmerkungen beschrieben. Diese sind im Namespace **urn:schemas\-microsoft\-com:xml\-msdata** definiert.  
  
|Anmerkung|Beschreibung|  
|---------------|------------------|  
|**RowOrder**|Behält die Zeilenreihenfolge der ursprünglichen Daten bei und gibt den Index einer Zeile in einer bestimmten <xref:System.Data.DataTable> an.|  
|**Hidden**|Gibt an, dass die **ColumnMapping**\-Eigenschaft einer Spalte auf **MappingType.Hidden** festgelegt ist.  Das Attribut ist im Format **msdata:hidden** *\[Spaltenname\]*\="*Wert*" geschrieben.  Beispiel: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Beachten Sie, dass ausgeblendete Spalten nur als DiffGram\-Attribut geschrieben werden, wenn sie Daten enthalten.  Andernfalls werden sie ignoriert.|  
  
## Beispiel für ein DiffGram  
 Unten ist ein Beispiel für das DiffGram\-Format aufgeführt.  In diesem Beispiel wird das Ergebnis des Updates einer Tabellenzeile veranschaulicht, bevor ein Commit der Änderungen ausgeführt wird.  Die Zeile mit der CustomerID "ALFKI" wurde geändert, jedoch nicht aktualisiert.  Dementsprechend enthält der **\<** ***DataInstance*** **\>**\-Block eine **Current**\-Zeile mit einer **diffgr:id** von "Customers1", und der **\<diffgr:before\>**\-Block enthält eine **Original**\-Zeile mit einer **diffgr:id** von "Customers1".  Die Zeile mit der CustomerID "ANATR" enthält einen **RowError**. Daher ist sie mit der Anmerkung `diffgr:hasErrors="true"` versehen, und der **\<diffgr:errors\>**\-Block enthält ein entsprechendes Element.  
  
```  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## Siehe auch  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Schreiben von 'DataSet'\-Inhalt als XML\-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)