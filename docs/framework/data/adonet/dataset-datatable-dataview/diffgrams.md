---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2c521ef33c98234dac5f4b819a800cd524218462
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151155"
---
# <a name="diffgrams"></a>DiffGrams
Ein DiffGram ist ein XML-Format, das aktuelle und ursprüngliche Versionen von Datenelementen angibt. <xref:System.Data.DataSet> verwendet das DiffGram-Format, um seinen Inhalt zu laden und beizubehalten und um seinen Inhalt für die Übertragung über eine Netzwerkverbindung zu serialisieren. Wenn <xref:System.Data.DataSet> ein als DiffGram geschrieben wird, füllt es das DiffGram mit allen erforderlichen Informationen auf, um <xref:System.Data.DataSet>den Inhalt, wenn auch nicht das Schema, des genau neu zu erstellen, einschließlich Spaltenwerten aus der **ursprünglichen** und **aktuellen** Zeilenversion, Zeilenfehlerinformationen und Zeilenreihenfolge.  
  
 Beim Senden und Abrufen eines <xref:System.Data.DataSet> über einen XML-Webdienst wird das DiffGram-Format implizit verwendet. Darüber hinaus können Sie <xref:System.Data.DataSet> beim Laden des Inhalts einer aus XML mithilfe <xref:System.Data.DataSet> der **ReadXml-Methode** oder beim Schreiben des Inhalts einer in XML mithilfe der **WriteXml-Methode** angeben, dass der Inhalt als DiffGram gelesen oder geschrieben werden soll. Weitere Informationen finden Sie unter [Laden eines DataSets aus XML](loading-a-dataset-from-xml.md) und Schreiben von [DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md).  
  
 Während das DiffGram-Format von .NET Framework primär als Serialisierungsformat für den Inhalt eines <xref:System.Data.DataSet> verwendet wird, können Sie mithilfe von DiffGrams auch Daten in Tabellen einer Microsoft SQL Server-Datenbank ändern.  
  
 Ein Diffgramm wird generiert, indem der Inhalt aller Tabellen in ein ** \<diffgram>-Element** geschrieben wird.  
  
### <a name="to-generate-a-diffgram"></a>So generieren Sie ein Diffgram  
  
1. Generieren Sie eine Liste von Stammtabellen (also Tabellen ohne irgendein übergeordnetes Element).  
  
2. Geben Sie im ersten Diffgram-Abschnitt für jede Tabelle und ihre untergeordneten Tabellen in der Liste die aktuelle Version der einzelnen Zeilen an.  
  
3. Schreiben Sie für <xref:System.Data.DataSet>jede Tabelle im die originale Version aller Zeilen(en) im ** \<Abschnitt "Vor>** des Diffgramms aus.  
  
4. Schreiben Sie bei Zeilen mit Fehlern ** \<** den Fehlerinhalt in den>Abschnitt des Diffgramms.  
  
 Ein Diffgram wird vom Anfang der XML-Datei bis zu deren Ende verarbeitet.  
  
### <a name="to-process-a-diffgram"></a>So verarbeiten Sie ein Diffgram  
  
1. Verarbeiten Sie den ersten Abschnitt des Diffgram, der die aktuelle Version der Zeilen enthält.  
  
2. Verarbeiten Sie den zweiten oder ** \<den vor>** Abschnitt, der die ursprüngliche Zeilenversion geänderter und gelöschter Zeilen enthält.  
  
    > [!NOTE]
    > Wenn eine Zeile als gelöscht gekennzeichnet ist, kann je nach der `Cascade`-Eigenschaft des aktuellen <xref:System.Data.DataSet> der Löschvorgang auch die untergeordneten Zeilen der Zeile löschen.  
  
3. Verarbeiten ** \<** Sie die Fehler>Abschnitt. Legen Sie in diesem Abschnitt die Fehlerinformationen für die angegebene Zeile und Spalte für jedes Element fest.  
  
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
  
 **\<**  ***Datainstance***  **>**  
 Der Name dieses Elements, ***DataInstance***, wird zu Erklärungszwecken in dieser Dokumentation verwendet. Ein ***DataInstance-Element*** stellt eine <xref:System.Data.DataSet> <xref:System.Data.DataTable>oder eine Zeile einer dar. Anstelle von *DataInstance*würde das Element <xref:System.Data.DataSet> den <xref:System.Data.DataTable>Namen der oder enthalten. Dieser Block des DiffGram-Formats enthält die aktuellen Daten, wobei es keine Rolle spielt, ob diese ggf. geändert wurden. Ein Element oder eine Zeile, das geändert wurde, wird mit der **annotation diffgr:hasChanges** identifiziert.  
  
 **\<diffgr:vor>**  
 Dieser Block des DiffGram-Formats enthält die ursprüngliche Version einer Zeile. Elemente in diesem Block werden mit Elementen im ***DataInstance-Block*** mithilfe der **diffgr:id-Anmerkung** abgeglichen.  
  
 **\<diffgr:fehler>**  
 Dieser Block des DiffGram-Formats enthält Fehlerinformationen für eine bestimmte Zeile im ***DataInstance-Block.*** Elemente in diesem Block werden mit Elementen im ***DataInstance-Block*** mithilfe der **diffgr:id-Anmerkung** abgeglichen.  
  
## <a name="diffgram-annotations"></a>DiffGram-Anmerkungen  
 In DiffGrams wird eine Reihe von Anmerkungen verwendet, um auf Elemente aus den verschiedenen DiffGram-Blöcken Bezug zu nehmen, die unterschiedliche Zeilenversionen oder Fehlerinformationen im <xref:System.Data.DataSet> darstellen.  
  
 In der folgenden Tabelle werden die DiffGram-Anmerkungen beschrieben, die im DiffGram-Namespace **urn:schemas-microsoft-com:xml-diffgram-v1**definiert sind.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**id**|Wird verwendet, um die Elemente in der **\<** **>** ** \<datei:vor>** und ** \<diffgr:errors>** Blöcke mit Elementen im ***DataInstance-Block*** zu koppeln. Werte mit der **diff:id-Anmerkung** haben die Form *[TableName][RowIdentifier]*. Beispiel: `<Customers diffgr:id="Customers1">`|  
|**Parentid**|Identifiziert, welches **\<** Element aus dem ***DataInstance-Block*** **>** das übergeordnete Element des aktuellen Elements ist. Werte mit der **annotation diffgr:parentId** haben die Form *[TableName][RowIdentifier]*. Beispiel: `<Orders diffgr:parentId="Customers1">`|  
|**hasChanges**|Identifiziert eine Zeile **\<** im ***DataInstance-Block*** **>** als geändert. Die **hasChanges-Anmerkung** kann einen der folgenden beiden Werte haben:<br /><br /> **Eingefügt**<br /> Identifiziert eine **hinzugefügte** Zeile.<br /><br /> **Geändert**<br /> Identifiziert eine **geänderte** Zeile, die eine **ursprüngliche** Zeilenversion im ** \<diffgr:before>-Block** enthält. Beachten Sie, dass **gelöschte** Zeilen eine **ursprüngliche** Zeilenversion im **\<** ** \<diffgr:before>-Block** haben, aber es gibt kein mit Anmerkungen beschriftetes Element im ***DataInstance-Block.*** **>**|  
|**hasErrors**|Identifiziert eine Zeile **\<** im ***DataInstance-Block*** **>** mit einem **RowError**. Das Fehlerelement wird im ** \<diffgr:errors>-Block** platziert.|  
|**Fehler**|Enthält den Text des **RowError** für ein bestimmtes Element im ** \<diffgr:errors->-Block.**|  
  
 Das <xref:System.Data.DataSet> enthält weitere Anmerkungen, wenn sein Inhalt als DiffGram gelesen oder geschrieben wird. In der folgenden Tabelle werden diese zusätzlichen Anmerkungen beschrieben, die im Namespace **urn:schemas-microsoft-com:xml-msdata**definiert sind.  
  
|Anmerkung|Beschreibung|  
|----------------|-----------------|  
|**RowOrder**|Behält die Zeilenreihenfolge der ursprünglichen Daten bei und gibt den Index einer Zeile in einer bestimmten <xref:System.Data.DataTable> an.|  
|**Versteckte**|Identifiziert eine Spalte als eine **ColumnMapping-Eigenschaft,** die auf **MappingType.Hidden**festgelegt ist. Das Attribut wird im Format **msdata:hidden** *[ColumnName]*="*geschrieben.* Beispiel: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`<br /><br /> Beachten Sie, dass ausgeblendete Spalten nur als DiffGram-Attribut geschrieben werden, wenn sie Daten enthalten. Andernfalls wird der Parameter ignoriert.|  
  
## <a name="sample-diffgram"></a>Beispiel für ein DiffGram  
 Unten ist ein Beispiel für das DiffGram-Format aufgeführt. In diesem Beispiel wird das Ergebnis des Updates einer Tabellenzeile veranschaulicht, bevor ein Commit der Änderungen ausgeführt wird. Die Zeile mit der CustomerID "ALFKI" wurde geändert, jedoch nicht aktualisiert. Daher gibt es eine **aktuelle** Zeile mit einer **diffgr:id** von **\<** "Customers1" im ***DataInstance-Block*** **>** und eine **Originalzeile** mit einer **diffgr:id** von "Customers1" im ** \<diffgr:before**>-Block. Die Zeile mit einer CustomerID von "ANATR" enthält einen **RowError**, sodass er mit `diffgr:hasErrors="true"` Anmerkungen mit einem zugehörigen Element im ** \<diffgr:errors->-Block** enthält.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von XML in einem "DataSet"](using-xml-in-a-dataset.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
