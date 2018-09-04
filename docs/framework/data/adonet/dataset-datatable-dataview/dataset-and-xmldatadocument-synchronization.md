---
title: DataSet- und XmlDataDocument-Synchronisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 54991234d4eaa9edab218d3b0d221a6e477d2be5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530085"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>DataSet- und XmlDataDocument-Synchronisierung
Das ADO.NET-<xref:System.Data.DataSet> stellt Daten relational dar. Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML-Klassen verwenden. Diese beiden Datendarstellungen wurden bisher immer separat verwendet. Allerdings ermöglicht .NET Framework einen synchronen Echtzeitzugriff auf die relationale und hierarchische Darstellung von Daten mithilfe der **DataSet** Objekt und die <xref:System.Xml.XmlDataDocument> Zielabhängigkeitsobjekt.  
  
 Wenn eine **DataSet** mit synchronisiert eine **XmlDataDocument**, arbeiten beide Objekte mit einem einzigen Satz von Daten. Dies bedeutet, dass eine Änderung vorgenommen wird, um die **DataSet**, die Änderung der **XmlDataDocument**, und umgekehrt. Die Beziehung zwischen der **DataSet** und **XmlDataDocument** erstellt Flexibilität durch eine einzelne Anwendung, die mit von einem einzigen Satz von Daten, auf die gesamte Suite von integrierten Dienste zugreifen können um die **DataSet** (z. B. Web Forms und Windows Forms-Steuerelemente und Designern für Visual Studio .NET) sowie die Sammlung von XML-Webdiensten, einschließlich Extensible Stylesheet Language (XSL), XSL Transformations (XSLT) und XML-Pfad Language (XPath). Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.  
  
 Es gibt mehrere Möglichkeiten, die Sie synchronisieren können eine **DataSet** mit einer **XmlDataDocument**. Sie haben folgende Möglichkeiten:  
  
-   Auffüllen einer **DataSet** mit Schema (d. h. einer relationalen Struktur) und die Daten und synchronisieren sie mit einem neuen **XmlDataDocument**. Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten. Zum Beispiel:  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   Auffüllen einer **DataSet** Typ schema only (wie z. B. eine stark typisierte **DataSet**), synchronisieren sie mit eine **XmlDataDocument**, und Laden Sie die  **XmlDataDocument** aus einem XML-Dokument. Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten. Die Tabellen- und Spaltennamen müssen in Ihre **DataSet** Schema übereinstimmen die Namen der XML-Elemente, die Sie mit synchronisiert werden sollen. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
     Beachten Sie, dass das Schema der **DataSet** muss nur die XML-Elemente übereinstimmen, die Sie in der relationalen Ansicht verfügbar machen möchten. Folglich können Sie ein sehr großes XML-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben. Die **XmlDataDocument** behält Sie das gesamte XML-Dokument, obwohl die **DataSet** stellt nur einen kleinen Teil davon. (Ein ausführliches Beispiel dieses finden Sie unter [Synchronisieren eines Datasets mit einem XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     Das folgende Codebeispiel zeigt die Schritte zum Erstellen einer **DataSet** und Füllen von dessen Schema sowie zum anschließenden Synchronisieren mit einem **XmlDataDocument**. Beachten Sie, dass die **DataSet** Schema muss nur die Elemente entsprechend dem **XmlDataDocument** , die Sie verfügbar machen, verwenden möchten die **DataSet**.  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     Sie können nicht geladen werden ein **XmlDataDocument** , wenn er mit synchronisiert wird eine **DataSet** , das Daten enthält. In diesem Fall wird eine Ausnahme ausgelöst.  
  
-   Erstellen Sie ein neues **XmlDataDocument** aus einem XML-Dokument laden, und klicken Sie dann Zugriff auf die relationale Ansicht der Daten mithilfe der **DataSet** Eigenschaft der **XmlDataDocument**. Müssen Sie das Schema der Festlegen der **DataSet** , bevor Sie die Daten in anzeigen können die **XmlDataDocument** mithilfe der **DataSet**. In diesem Fall die Tabellen- und Spaltennamen im Namen Ihrer **DataSet** Schema übereinstimmen die Namen der XML-Elemente, die Sie mit synchronisiert werden sollen. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie die relationale Ansicht der Daten in den Zugriff auf eine **XmlDataDocument**.  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 Ein weiterer Vorteil der Synchronisierung ein **XmlDataDocument** mit einem **DataSet** besteht darin, dass die Genauigkeit eines XML-Dokuments beibehalten wird. Wenn die **DataSet** wird aus einer XML-Dokument mit aufgefüllt **ReadXml**, wenn die Daten als XML-Dokument mit zurückgeschrieben werden **WriteXml** sie möglicherweise die unterscheiden sich erheblich, von der ursprüngliche XML-Dokument. Grund hierfür ist die **DataSet** behält keine Formatierung, z. B. leer- oder hierarchische Informationen, wie die Reihenfolge der Elemente, aus dem XML-Dokument. Die **DataSet** auch keine Elemente aus dem XML-Dokument, das ignoriert wurden, da sie nicht das Schema der entspricht der **Dataset**. Synchronisieren einer **XmlDataDocument** mit einer **DataSet** ermöglicht die Formatierungen und die hierarchische Elementstruktur des ursprünglichen XML-Dokuments im beibehalten werden die **XmlDataDocument**, während die **DataSet** enthält nur Daten und Schema für die **DataSet**.  
  
 Bei der Synchronisierung ein **DataSet** mit einer **XmlDataDocument**, Ergebnisse hängen davon ab, ob Ihre <xref:System.Data.DataRelation> -Objekte geschachtelt sind. Weitere Informationen finden Sie unter [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Synchronisieren eines DataSet mit einem XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Demonstriert die Synchronisierung eine stark typisierte **DataSet**, mit dem Schema "minimal", mit einem **XmlDataDocument**.  
  
 [Ausführen einer XPath-Abfrage für ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Veranschaulicht die Ausführung einer XPath-Abfrage auf dem Inhalt einer **DataSet**.  
  
 [Anwenden einer XSLT-Transformation auf ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Veranschaulicht die Anwendung einer XSLT-Transformation auf den Inhalt einer **DataSet**.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie die **DataSet** interagiert mit XML als Datenquelle, einschließlich des Ladens und Beibehaltens des Inhalts einer **DataSet** als XML-Daten.  
  
 [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Erläutert die Bedeutung geschachtelter **DataRelation** -Objekte beim Darstellen des Inhalts einer **DataSet** als XML-Daten, und beschreibt, wie diese Beziehungen zu erstellen.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt die **DataSet** und wie Sie es verwenden, um Anwendungsdaten zu verwalten und für die Interaktion mit Datenquellen, einschließlich relationaler Datenbanken und XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Enthält Referenzinformationen zu den **XmlDataDocument** Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
