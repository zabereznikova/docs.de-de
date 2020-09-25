---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: aff9c2347fab51d853e19bd9dc16666c4ed549b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172800"
---
# <a name="diffgrams"></a>DiffGrams

Ein DiffGram ist ein XML-Format, das aktuelle und ursprüngliche Versionen von Datenelementen angibt. <xref:System.Data.DataSet> verwendet das DiffGram-Format, um seinen Inhalt zu laden und beizubehalten und um seinen Inhalt für die Übertragung über eine Netzwerkverbindung zu serialisieren. Wenn eine <xref:System.Data.DataSet> als DiffGram geschrieben wird, füllt Sie das DiffGram mit allen erforderlichen Informationen aus, um den Inhalt, aber nicht das Schema, ordnungsgemäß neu zu erstellen, <xref:System.Data.DataSet> einschließlich der Spaltenwerte aus der **ursprünglichen** und der **aktuellen** Zeilen Version, Zeilen Fehlerinformationen und Zeilen Reihenfolge.  
  
 Beim Senden und Abrufen eines <xref:System.Data.DataSet> über einen XML-Webdienst wird das DiffGram-Format implizit verwendet. Außerdem können Sie beim Laden des Inhalts eines <xref:System.Data.DataSet> aus XML mithilfe der Methode "read **XML** " oder beim Schreiben des Inhalts eines <xref:System.Data.DataSet> in XML mithilfe der **WriteXml** -Methode angeben, dass der Inhalt als DiffGram gelesen oder geschrieben werden soll. Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](loading-a-dataset-from-xml.md) und [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md).  
  
 Während das DiffGram-Format von .NET Framework primär als Serialisierungsformat für den Inhalt eines <xref:System.Data.DataSet> verwendet wird, können Sie mithilfe von DiffGrams auch Daten in Tabellen einer Microsoft SQL Server-Datenbank ändern.  
  
 Ein DiffGram wird generiert, indem der Inhalt aller Tabellen in ein- **\<diffgram>** Element geschrieben wird.  
  
### <a name="to-generate-a-diffgram"></a>So generieren Sie ein Diffgram  
  
1. Generieren Sie eine Liste von Stammtabellen (also Tabellen ohne irgendein übergeordnetes Element).  
  
2. Geben Sie im ersten Diffgram-Abschnitt für jede Tabelle und ihre untergeordneten Tabellen in der Liste die aktuelle Version der einzelnen Zeilen an.  
  
3. Schreiben Sie für jede Tabelle in die <xref:System.Data.DataSet> ursprüngliche Version aller Zeilen (sofern vorhanden) im- **\<before>** Abschnitt des DiffGram-Abschnitts.  
  
4. Schreiben Sie für Zeilen mit Fehlern den Fehler Inhalt in den **\<errors>** Abschnitt des DiffGram-Abschnitts.  
  
 Ein Diffgram wird vom Anfang der XML-Datei bis zu deren Ende verarbeitet.  
  
### <a name="to-process-a-diffgram"></a>So verarbeiten Sie ein Diffgram  
  
1. Verarbeiten Sie den ersten Abschnitt des Diffgram, der die aktuelle Version der Zeilen enthält.  
  
2. Verarbeiten Sie den zweiten Abschnitt oder den **\<before>** Abschnitt, der die Original Zeilen Version der geänderten und gelöschten Zeilen enthält.  
  
    > [!NOTE]
    > Wenn eine Zeile als gelöscht gekennzeichnet ist, kann je nach der `Cascade`-Eigenschaft des aktuellen <xref:System.Data.DataSet> der Löschvorgang auch die untergeordneten Zeilen der Zeile löschen.  
  
3. Verarbeiten Sie den **\<errors>** Abschnitt. Legen Sie in diesem Abschnitt die Fehlerinformationen für die angegebene Zeile und Spalte für jedes Element fest.  
  
> [!NOTE]
> Wenn Sie für <xref:System.Data.XmlWriteMode> "Diffgram" festlegen, kann es passieren, dass sich der Inhalt des Ziel-<xref:System.Data.DataSet> und des Original-<xref:System.Data.DataSet> voneinander unterscheiden.  
  
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
 Der Name dieses Elements, ***DataInstance***, wird zur Erläuterung in dieser Dokumentation verwendet. Ein ***DataInstance*** -Element stellt ein <xref:System.Data.DataSet> oder eine Zeile eines dar <xref:System.Data.DataTable> . Anstelle von *DataInstance*würde das-Element den Namen von oder enthalten <xref:System.Data.DataSet> <xref:System.Data.DataTable> . Dieser Block des DiffGram-Formats enthält die aktuellen Daten, wobei es keine Rolle spielt, ob diese ggf. geändert wurden. Ein Element oder eine Zeile, das geändert wurde, wird mit der **diffgr: hasChanges** -Anmerkung identifiziert.  
  
 **\<diffgr:before>**  
 Dieser Block des DiffGram-Formats enthält die ursprüngliche Version einer Zeile. Elemente in diesem Block werden mithilfe der **diffgr: ID** -Anmerkung mit Elementen im ***DataInstance*** -Block abgeglichen.  
  
 **\<diffgr:errors>**  
 Dieser Block des DiffGram-Formats enthält Fehlerinformationen für eine bestimmte Zeile im ***DataInstance*** -Block. Elemente in diesem Block werden mithilfe der **diffgr: ID** -Anmerkung mit Elementen im ***DataInstance*** -Block abgeglichen.  
  
## <a name="diffgram-annotations"></a>DiffGram-Anmerkungen  

 In DiffGrams wird eine Reihe von Anmerkungen verwendet, um auf Elemente aus den verschiedenen DiffGram-Blöcken Bezug zu nehmen, die unterschiedliche Zeilenversionen oder Fehlerinformationen im <xref:System.Data.DataSet> darstellen.  
  
 In der folgenden Tabelle werden die DiffGram-Anmerkungen beschrieben, die im DiffGram-Namespace **urn: Schemas-Microsoft-com: XML-DiffGram-v1**definiert sind.  
  
|Anmerkung|BESCHREIBUNG|  
|----------------|-----------------|  
|**id**|Wird verwendet, um die Elemente in den **\<diffgr:before>** -und- **\<diffgr:errors>** Blöcken den Elementen im-Block zu koppeln **\<** ***DataInstance*** **>** . Werte mit der **diffgr: ID** -Anmerkung haben das Format *[Tabellenname] [rowidentifier]*. Beispiel: `<Customers diffgr:id="Customers1">`.|  
|**parentID**|Gibt an, welches Element aus dem- **\<** ***DataInstance*** **>** Block das übergeordnete Element des aktuellen Elements ist. Werte mit der **diffgr: Element-ID-** Anmerkung haben das Format *[Tabellenname] [rowidentifier]*. Beispiel: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifiziert eine Zeile im- **\<** ***DataInstance*** **>** Block als geändert. Die **hasChanges** -Anmerkung kann einen der folgenden beiden Werte aufweisen:<br /><br /> **gelegte**<br /> Identifiziert eine **hinzugefügte** Zeile.<br /><br /> **geändert**<br /> Identifiziert eine **geänderte** Zeile, die eine **Original** -Zeilen Version im- **\<diffgr:before>** Block enthält. Beachten Sie, dass **Gelöschte** Zeilen über eine **Original** -Zeilen Version im- **\<diffgr:before>** Block verfügen, aber im-Block kein Element mit Anmerkungen vorhanden ist **\<** ***DataInstance*** **>** .|  
|**hasErrors**|Identifiziert eine Zeile im- **\<** ***DataInstance*** **>** Block mit einem **RowError**. Das Error-Element wird in den- **\<diffgr:errors>** Block eingefügt.|  
|**Fehler**|Enthält den Text des **RowError** für ein bestimmtes Element im- **\<diffgr:errors>** Block.|  
  
 Das <xref:System.Data.DataSet> enthält weitere Anmerkungen, wenn sein Inhalt als DiffGram gelesen oder geschrieben wird. In der folgenden Tabelle werden diese zusätzlichen Anmerkungen beschrieben, die im Namespace **urn: Schemas-Microsoft-com: XML-Msdata**definiert sind.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**RowOrder**|Behält die Zeilenreihenfolge der ursprünglichen Daten bei und gibt den Index einer Zeile in einer bestimmten <xref:System.Data.DataTable> an.|  
|**Hidden**|Gibt an, dass eine Spalte als **ColumnMapping** -Eigenschaft auf **MappingType. Hidden**festgelegt ist. Das Attribut ist im Format **msdata: Hidden** *[columnName]*= "*value*" geschrieben. Beispiel: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Beachten Sie, dass ausgeblendete Spalten nur als DiffGram-Attribut geschrieben werden, wenn sie Daten enthalten. Andernfalls wird der Parameter ignoriert.|  
  
## <a name="sample-diffgram"></a>Beispiel für ein DiffGram  

 Unten ist ein Beispiel für das DiffGram-Format aufgeführt. In diesem Beispiel wird das Ergebnis des Updates einer Tabellenzeile veranschaulicht, bevor ein Commit der Änderungen ausgeführt wird. Die Zeile mit der CustomerID "ALFKI" wurde geändert, jedoch nicht aktualisiert. Folglich gibt es eine **aktuelle** Zeile mit der **diffgr: ID** "Customers1" im **\<** ***DataInstance*** **>** -Block und eine **ursprüngliche** Zeile mit der **diffgr: ID** "Customers1" im- **\<diffgr:before>** Block. Die Zeile mit der CustomerID "ANATR" enthält einen **RowError**, sodass Sie mit versehen ist `diffgr:hasErrors="true"` und ein verwandtes Element im-Block vorhanden ist **\<diffgr:errors>** .  
  
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

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
