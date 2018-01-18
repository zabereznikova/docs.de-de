---
title: DataSet- und XmlDataDocument-Synchronisierung
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
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9cdfdf01b950d13ba77f76b126fe6d2ff430ef07
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>DataSet- und XmlDataDocument-Synchronisierung
Das ADO.NET-<xref:System.Data.DataSet> stellt Daten relational dar. Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML-Klassen verwenden. Diese beiden Datendarstellungen wurden bisher immer separat verwendet. Allerdings ermöglicht .NET Framework synchronen Zugriff auf die relationale bzw. die hierarchische Darstellung von Daten über die **DataSet** Objekt und die <xref:System.Xml.XmlDataDocument> -Objekts.  
  
 Wenn eine **DataSet** mit synchronisiert eine **XmlDataDocument**, arbeiten beide Objekte mit einem einzelnen Satz von Daten. Dies bedeutet, dass wenn eine Änderung, um vorgenommen wird die **DataSet**, die Änderung wird der **XmlDataDocument**, und umgekehrt. Die Beziehung zwischen der **DataSet** und **XmlDataDocument** maximale Flexibilität beim erstellt, können Sie eine einzelne Anwendung, die über einen einzelnen Satz von Daten, auf die ganze Sammlung von integrierten Dienste zugreifen um die **DataSet** (z. B. Web Forms- und Windows Forms-Steuerelemente und Designer für Visual Studio .NET), sowie die Sammlung von XML-Webdiensten, einschließlich Extensible Stylesheet Language (XSL), XSL-Transformationen (XSLT) und XML-Pfad Language (XPath). Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.  
  
 Es gibt mehrere Möglichkeiten, die Sie synchronisieren können eine **DataSet** mit einem **XmlDataDocument**. Sie haben folgende Möglichkeiten:  
  
-   Auffüllen einer **DataSet** mit einem Schema (d. h. einer relationalen Struktur) und Daten und synchronisieren Sie es mit einem neuen **XmlDataDocument**. Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten. Zum Beispiel:  
  
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
  
-   Auffüllen einer **DataSet** vom Typ Schema only (z. B. ein stark typisiertes **DataSet**), Synchronisieren mit eine **XmlDataDocument**, und Laden Sie die  **XmlDataDocument** aus einem XML-Dokument. Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten. Die Tabellen- und Spaltennamen müssen in Ihre **DataSet** Schema muss den Namen der XML-Elemente, die Sie mit synchronisiert werden sollen übereinstimmen. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
     Beachten Sie, dass das Schema der **DataSet** muss nur die XML-Elemente übereinstimmen, die Sie in der relationalen Ansicht verfügbar machen möchten. Folglich können Sie ein sehr großes XML-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben. Die **XmlDataDocument** behält Sie das gesamte XML-Dokument, obwohl die **DataSet** macht nur eine kleine Teilmenge davon verfügbar. (Ein ausführliches Beispiel hierfür finden Sie unter [Synchronisieren eines Datasets mit einem XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     Das folgende Codebeispiel zeigt die Schritte zum Erstellen einer **DataSet** und Füllen von dessen Schema sowie zum anschließenden Synchronisieren mit einer **XmlDataDocument**. Beachten Sie, dass die **DataSet** Schema muss nur die Elemente entsprechend der **XmlDataDocument** , die Sie verfügbar machen, verwenden möchten die **DataSet**.  
  
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
  
     Sie können nicht geladen werden ein **XmlDataDocument** , wenn er mit synchronisiert ist ein **DataSet** , das Daten enthält. In diesem Fall wird eine Ausnahme ausgelöst.  
  
-   Erstellen Sie ein neues **XmlDataDocument** aus einem XML-Dokument zu laden und dann Zugriff auf die relationale Ansicht der Daten unter Verwendung der **DataSet** Eigenschaft von der **XmlDataDocument**. Müssen Sie das Schema der Festlegen der **DataSet** , bevor Sie die Daten in anzeigen können den **XmlDataDocument** mithilfe der **DataSet**. Die Tabellen- und Spaltennamen erneut, den Namen Ihrer **DataSet** Schema muss den Namen der XML-Elemente, die Sie mit synchronisiert werden sollen übereinstimmen. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
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
  
 Ein weiterer Vorteil der Synchronisierung ein **XmlDataDocument** mit einem **DataSet** ist, dass das von einem XML-Dokument erhalten bleibt. Wenn die **DataSet** wird aus einer XML-Dokument mit aufgefüllt **ReadXml**, wenn die Daten als eine XML-Dokument mit zurückgeschrieben werden **WriteXml** es unterscheidet sich möglicherweise deutlich von der ursprüngliche XML-Dokument. Grund hierfür ist die **DataSet** behält keine Formatierung, z. B. leer- oder hierarchische Informationen, z. B. die Reihenfolge der Elemente, aus dem XML-Dokument. Die **DataSet** enthält auch keine Elemente aus dem XML-Dokument, das ignoriert wurden, da sie nicht das Schema der entspricht der **Dataset**. Synchronisiert ein **XmlDataDocument** mit einer **DataSet** ermöglicht die Formatierungen und die hierarchische Elementstruktur des ursprünglichen XML-Dokuments in beibehalten werden die **XmlDataDocument**, während die **DataSet** nur Daten und Schemainformationen enthält, die die **DataSet**.  
  
 Bei der Synchronisierung einer **DataSet** mit einer **XmlDataDocument**, Ergebnisse unterscheiden sich möglicherweise, abhängig davon, ob Ihre <xref:System.Data.DataRelation> -Objekte geschachtelt sind. Weitere Informationen finden Sie unter [Schachteln von "DataRelations"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Synchronisieren eines DataSet mit einem XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Veranschaulicht die Synchronisierung eines stark typisierten **DataSet**, mit minimalistischem Schema mit einem **XmlDataDocument**.  
  
 [Ausführen einer XPath-Abfrage für ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Veranschaulicht die Ausführung einer XPath-Abfrage auf dem Inhalt einer **DataSet**.  
  
 [Anwenden einer XSLT-Transformation auf ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Veranschaulicht das Anwenden einer XSLT-Transformation auf den Inhalt einer **DataSet**.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie die **DataSet** interagiert mit XML als Datenquelle, einschließlich des Ladens und Beibehaltens des Inhalts einer **DataSet** als XML-Daten.  
  
 [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Erläutert die Bedeutung geschachtelter **DataRelation** -Objekte beim Darstellen des Inhalts einer **DataSet** als XML-Daten und beschreibt, wie diese Beziehungen zu erstellen.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt die **DataSet** und wie es zum Verwalten von Anwendungsdaten und interagieren mit Datenquellen, einschließlich relationaler Datenbanken und XML verwendet.  
  
 <xref:System.Xml.XmlDataDocument>  
 Enthält Referenzinformationen zu den **XmlDataDocument** Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
