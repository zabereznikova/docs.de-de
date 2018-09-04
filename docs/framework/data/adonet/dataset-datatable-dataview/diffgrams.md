---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: fd452efff2a26b66c06a7762b215df140047286d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43558326"
---
# <a name="diffgrams"></a>DiffGrams
Ein DiffGram ist ein XML-Format, das aktuelle und ursprüngliche Versionen von Datenelementen angibt. <xref:System.Data.DataSet> verwendet das DiffGram-Format, um seinen Inhalt zu laden und beizubehalten und um seinen Inhalt für die Übertragung über eine Netzwerkverbindung zu serialisieren. Wenn eine <xref:System.Data.DataSet> wird als DiffGram geschrieben, füllt es das DiffGram mit allen erforderlichen Informationen, um genau den Inhalt, jedoch nicht mit das Schema, der neu zu erstellen die <xref:System.Data.DataSet>, einschließlich Spaltenwerten aus der **ursprünglichen** und **aktuelle** Zeilenversionen, Zeilenfehlerinformationen und Zeilenreihenfolgen.  
  
 Beim Senden und Abrufen eines <xref:System.Data.DataSet> über einen XML-Webdienst wird das DiffGram-Format implizit verwendet. Darüber hinaus beim Laden des Inhalts einer <xref:System.Data.DataSet> aus XML mithilfe der **ReadXml** -Methode, oder beim Schreiben des Inhalts einer <xref:System.Data.DataSet> in XML mithilfe der **WriteXml** -Methode, die Sie angeben können dass der Inhalt gelesen oder als DiffGram geschrieben werden. Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Schreiben von DataSet-Inhalten als XML-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Während das DiffGram-Format von .NET Framework primär als Serialisierungsformat für den Inhalt eines <xref:System.Data.DataSet> verwendet wird, können Sie mithilfe von DiffGrams auch Daten in Tabellen einer Microsoft SQL Server-Datenbank ändern.  
  
 Ein Diffgram wird generiert, indem Sie schreiben den Inhalt aller Tabellen in einem  **\<Diffgram >** Element.  
  
### <a name="to-generate-a-diffgram"></a>So generieren Sie ein Diffgram  
  
1.  Generieren Sie eine Liste von Stammtabellen (also Tabellen ohne irgendein übergeordnetes Element).  
  
2.  Geben Sie im ersten Diffgram-Abschnitt für jede Tabelle und ihre untergeordneten Tabellen in der Liste die aktuelle Version der einzelnen Zeilen an.  
  
3.  Für jede Tabelle in der <xref:System.Data.DataSet>, schreiben die Originalversion der einzelnen Zeilen an, sofern vorhanden, in der  **\<vor >** Abschnitt des DiffGram-Objekts.  
  
4.  Für Zeilen mit Fehlermeldungen der Fehlermeldung die  **\<Fehlern >** Abschnitt des DiffGram-Objekts.  
  
 Ein Diffgram wird vom Anfang der XML-Datei bis zu deren Ende verarbeitet.  
  
### <a name="to-process-a-diffgram"></a>So verarbeiten Sie ein Diffgram  
  
1.  Verarbeiten Sie den ersten Abschnitt des Diffgram, der die aktuelle Version der Zeilen enthält.  
  
2.  Verarbeiten Sie den zweiten oder  **\<vor >** Abschnitt mit die Originalversion der bearbeiteten und gelöschten Zeilen.  
  
    > [!NOTE]
    >  Wenn eine Zeile als gelöscht gekennzeichnet ist, kann je nach der `Cascade`-Eigenschaft des aktuellen <xref:System.Data.DataSet> der Löschvorgang auch die untergeordneten Zeilen der Zeile löschen.  
  
3.  Prozess der  **\<Fehlern >** Abschnitt. Legen Sie in diesem Abschnitt die Fehlerinformationen für die angegebene Zeile und Spalte für jedes Element fest.  
  
> [!NOTE]
>  Wenn Sie für <xref:System.Data.XmlWriteMode> "Diffgram" festlegen, kann es passieren, dass sich der Inhalt des Ziel-<xref:System.Data.DataSet> und des Original-<xref:System.Data.DataSet> voneinander unterscheiden.  
  
## <a name="diffgram-format"></a>DiffGram-Format  
 Das DiffGram-Format ist in drei Abschnitte unterteilt: die aktuellen Daten, die ursprünglichen (oder "vorher") Daten und ein Fehlerabschnitt, wie im folgenden Beispiel dargestellt.  
  
```xml  
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
  
 Das DiffGram-Format umfasst die folgenden Datenblöcke:  
  
 **\<**  ***DataInstance***  **>**  
 Der Name dieses Elements ***DataInstance***, wird in dieser Dokumentation zu Erklärungszwecken verwendet. Ein ***DataInstance*** Element darstellt, ein <xref:System.Data.DataSet> oder eine Zeile einer <xref:System.Data.DataTable>. Anstelle von *DataInstance*, das Element enthält den Namen der <xref:System.Data.DataSet> oder <xref:System.Data.DataTable>. Dieser Block des DiffGram-Formats enthält die aktuellen Daten, wobei es keine Rolle spielt, ob diese ggf. geändert wurden. Ein Element oder die Zeile, die geändert wurde, wird mit identifiziert die **diffgr: HasChanges** Anmerkung.  
  
 **\<diffgr:before>**  
 Dieser Block des DiffGram-Formats enthält die ursprüngliche Version einer Zeile. Elemente in diesem Block werden verglichen, auf Elemente in der ***DataInstance*** mit blockiert die **diffgr: ID** Anmerkung.  
  
 **\<diffgr:errors>**  
 Dieser Block des DiffGram-Formats enthält Fehlerinformationen für eine bestimmte Zeile in der ***DataInstance*** Block. Elemente in diesem Block werden verglichen, auf Elemente in der ***DataInstance*** mit blockiert die **diffgr: ID** Anmerkung.  
  
## <a name="diffgram-annotations"></a>DiffGram-Anmerkungen  
 In DiffGrams wird eine Reihe von Anmerkungen verwendet, um auf Elemente aus den verschiedenen DiffGram-Blöcken Bezug zu nehmen, die unterschiedliche Zeilenversionen oder Fehlerinformationen im <xref:System.Data.DataSet> darstellen.  
  
 Die folgende Tabelle beschreibt die DiffGram-Anmerkungen, die im DiffGram-Namespace definiert sind **Urn: Schemas-Microsoft-com: XML-Diffgram-v1**.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**ID**|Verwendet, um die Elemente in der  **\<Diffgr: vor dem >** und  **\<diffgr: errors >** Blöcke, um Elemente in der **\<** ***DataInstance*** **>** Block. Werte mit den **diffgr: ID** -Anmerkung haben das Format *[Tabellenname] [Zeilenbezeichner]*. Beispiel: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Gibt an, welches Element aus der **\<** ***DataInstance*** **>** Block ist das übergeordnete Element des aktuellen Elements. Werte mit den **diffgr: parentId** -Anmerkung haben das Format *[Tabellenname] [Zeilenbezeichner]*. Beispiel: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifiziert eine Zeile in der **\<** ***DataInstance*** **>** -Block als geändert. Die **HasChanges** -Anmerkung kann einen der folgenden zwei Werte aufweisen:<br /><br /> **inserted**<br /> Identifiziert eine **Added** Zeile.<br /><br /> **Geändert**<br /> Identifiziert eine **"geändert"** Zeile mit einer **ursprünglichen** Zeilenversion in der  **\<Diffgr: vor dem >** Block. Beachten Sie, dass **gelöschte** Zeilen müssen eine **ursprünglichen** Zeilenversion in der  **\<Diffgr: vor dem >** blockieren, aber es ist kein Element mit Anmerkungen in der **\<** ***DataInstance*** **>** Block.|  
|**hasErrors**|Identifiziert eine Zeile in der **\<** ***DataInstance*** **>** -block mit einer **RowError**. Das Fehlerelement wird der  **\<diffgr: errors >** Block.|  
|**Fehler**|Enthält den Text der **RowError** für ein bestimmtes Element in der  **\<diffgr: errors >** Block.|  
  
 Das <xref:System.Data.DataSet> enthält weitere Anmerkungen, wenn sein Inhalt als DiffGram gelesen oder geschrieben wird. Die folgende Tabelle beschreibt diese zusätzlichen Anmerkungen im Namespace definierten **Urn: Schemas-Microsoft-com: XML-Msdata**.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**RowOrder**|Behält die Zeilenreihenfolge der ursprünglichen Daten bei und gibt den Index einer Zeile in einer bestimmten <xref:System.Data.DataTable> an.|  
|**Ausgeblendet**|Identifiziert eine Spalte mit einem **ColumnMapping** -Eigenschaftensatz auf **MappingType.Hidden**. Das Attribut hat das Format **Msdata: ausgeblendete** *[Spaltenname]*= "*Wert*". Beispiel: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Beachten Sie, dass ausgeblendete Spalten nur als DiffGram-Attribut geschrieben werden, wenn sie Daten enthalten. Andernfalls werden sie ignoriert.|  
  
## <a name="sample-diffgram"></a>Beispiel für ein DiffGram  
 Unten ist ein Beispiel für das DiffGram-Format aufgeführt. In diesem Beispiel wird das Ergebnis des Updates einer Tabellenzeile veranschaulicht, bevor ein Commit der Änderungen ausgeführt wird. Die Zeile mit der CustomerID "ALFKI" wurde geändert, jedoch nicht aktualisiert. Daher besteht eine **aktuelle** -Zeile mit einer **diffgr: ID** von "Customers1", in der **\<** ***DataInstance*** **>** Block und ein **ursprünglichen** -Zeile mit einer **diffgr: ID** von "Customers1", in der  **\<Diffgr: vor dem >** Block. Die Zeile mit der CustomerID "ANATR" enthält einen **RowError**, sodass es mit Anmerkung versehen ist `diffgr:hasErrors="true"` und ein entsprechendes Element in der  **\<diffgr: errors >** Block.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Schreiben von DataSet-Inhalten als XML-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
