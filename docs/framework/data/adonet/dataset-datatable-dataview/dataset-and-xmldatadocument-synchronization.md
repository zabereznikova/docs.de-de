---
title: "Synchronisierung zwischen &#39;DataSet&#39; und &#39;XmlDataDocument&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Synchronisierung zwischen &#39;DataSet&#39; und &#39;XmlDataDocument&#39;
Das ADO.NET\-<xref:System.Data.DataSet> stellt Daten relational dar.  Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML\-Klassen verwenden.  Diese beiden Datendarstellungen wurden bisher immer separat verwendet.  Allerdings ermöglicht .NET Framework über das **DataSet**\-Objekt und das <xref:System.Xml.XmlDataDocument>\-Objekt einen synchronen Echtzeitzugriff auf die relationale bzw. die hierarchische Darstellung der Daten.  
  
 Wenn ein **DataSet** mit einem **XmlDataDocument** synchronisiert wird, arbeiten beide Objekte mit nur einem Datensatz.  Bei einer Änderung des **DataSet** wird die Änderung somit im **XmlDataDocument** angezeigt und umgekehrt.  Die Beziehung zwischen dem **DataSet** und dem **XmlDataDocument** sorgt für eine hohe Flexibilität, da eine einzelne Anwendung mithilfe eines einzelnen Datensatzes auf sämtliche Dienste, die um das **DataSet** aufgebaut wurden \(z. B. Web Forms\- und Windows Forms\-Steuerelemente sowie Visual Studio .NET\-Designer\) sowie auf das Paket der XML\-Dienste zugreifen kann, einschließlich Extensible Stylesheet Language \(XSL\), XSL\-Transformationen \(XSLT\) und XML Path Language \(XPath\).  Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.  
  
 Es bestehen mehrere Möglichkeiten, ein **DataSet** mit einem **XmlDataDocument** zu synchronisieren.  Sie haben folgende Möglichkeiten:  
  
-   Sie können ein **DataSet** mit einem Schema \(einer relationalen Struktur\) und Daten füllen und es dann mit einem neuen **XmlDataDocument** synchronisieren.  Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten.  Beispiel:  
  
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
  
-   Sie können ein **DataSet** nur mit einem Schema füllen \(z. B. einem **DataSet** mit strikter Typbindung\), es mit einem **XmlDataDocument** synchronisieren und das **XmlDataDocument** anschließend aus einem XML\-Dokument laden.  Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten.  Die im **DataSet**\-Schema enthaltenen Tabellen\- und Spaltennamen müssen mit den Namen der XML\-Elemente übereinstimmen, mit denen sie synchronisiert werden sollen.  Bei diesem Prozess wird die Groß\- und Kleinschreibung berücksichtigt.  
  
     Beachten Sie, dass das Schema des **DataSet** nur mit den XML\-Elementen übereinstimmen muss, die in der relationalen Ansicht verfügbar gemacht werden sollen.  Folglich können Sie ein sehr großes XML\-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben.  Das **XmlDataDocument** behält das gesamte XML\-Dokument bei, selbst wenn das **DataSet** nur eine kleine Teilmenge davon verfügbar macht.  \(Ein ausführliches Beispiel finden Sie unter [Synchronisieren eines 'DataSet' mit einem 'XmlDataDocument'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).\)  
  
     Im folgenden Codebeispiel werden die Schritte zum Erstellen eines **DataSet**, zum Füllen von dessen Schema sowie zum anschließenden Synchronisieren mit einem **XmlDataDocument** dargestellt.  Beachten Sie, dass das **DataSet**\-Schema nur mit den Elementen aus dem **XmlDataDocument** übereinstimmen muss, das Sie mit dem **DataSet** verfügbar machen möchten.  
  
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
  
     Ein **XmlDataDocument** kann nicht geladen werden, wenn es mit einem **DataSet** synchronisiert wird, das Daten enthält.  In diesem Fall wird eine Ausnahme ausgelöst.  
  
-   Erstellen Sie ein neues **XmlDataDocument**, und laden Sie es über ein XML\-Dokument. Greifen Sie anschließend mit der **DataSet**\-Eigenschaft von **XmlDataDocument** auf die relationale Ansicht der Daten zu.  Sie müssen das Schema des **DataSet** festlegen, bevor Sie die Daten im **XmlDataDocument** mit dem **DataSet** anzeigen können.  Die im **DataSet**\-Schema enthaltenen Tabellen\- und Spaltennamen müssen mit den Namen der XML\-Elemente übereinstimmen, mit denen sie synchronisiert werden sollen.  Bei diesem Prozess wird die Groß\- und Kleinschreibung berücksichtigt.  
  
     Im folgenden Beispiel wird dargestellt, wie auf die relationale Ansicht der Daten in einem **XmlDataDocument** zugegriffen wird.  
  
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
  
 Ein weiterer Vorteil der Synchronisierung eines **XmlDataDocument** mit einem **DataSet** besteht darin, dass das XML\-Dokument erhalten bleibt.  Wenn das **DataSet** über ein XML\-Dokument mit **ReadXml** gefüllt wird, kann das XML\-Dokument erheblich vom ursprünglichen XML\-Dokument abweichen, wenn die Daten mit **WriteXml** als XML\-Dokument zurückgeschrieben werden.  Der Grund dafür ist, dass das **DataSet** keine Formatierung \(z. B. Leerzeichen\) oder hierarchische Informationen \(z. B. die Elementfolge\) des XML\-Dokuments übernimmt.  Das **DataSet** enthält auch keine Elemente des XML\-Dokuments, die aufgrund der Nichtübereinstimmung mit dem Schema des **Dataset** ignoriert wurden.  Bei der Synchronisierung eines **XmlDataDocument** mit einem **DataSet** werden die Formatierungen und die hierarchische Elementstruktur des ursprünglichen XML\-Dokuments im **XmlDataDocument** beibehalten, während das **DataSet** nur Daten und Schemainformationen enthält, die für das **DataSet** relevant sind.  
  
 Bei der Synchronisierung eines **DataSet** mit einem **XmlDataDocument** können die Ergebnisse unterschiedlich ausfallen, je nachdem, ob die <xref:System.Data.DataRelation>\-Objekte geschachtelt sind oder nicht.  Weitere Informationen finden Sie unter [Schachteln von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## In diesem Abschnitt  
 [Synchronisieren eines 'DataSet' mit einem 'XmlDataDocument'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Veranschaulicht die Synchronisierung eines **DataSet** mit strikter Typbindung und minimalistischem Schema mit einem **XmlDataDocument**.  
  
 [Durchführen einer XPath\-Abfrage für ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Veranschaulicht die Ausführung einer XPath\-Abfrage für den Inhalt eines **DataSet**.  
  
 [Anwenden einer XSLT\-Transformation auf ein DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Veranschaulicht das Anwenden einer XSLT\-Transformation auf den Inhalt eines **DataSet**.  
  
## Verwandte Abschnitte  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie das **DataSet** mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines **DataSet** als XML\-Daten.  
  
 [Schachteln von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Erläutert die Bedeutung geschachtelter **DataRelation**\-Objekte beim Darstellen des Inhalts eines **DataSet** als XML\-Daten und beschreibt die Erstellung dieser Beziehungen.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt das **DataSet** und enthält Informationen zu dessen Verwendung beim Verwalten von Anwendungsdaten sowie zur Interaktion mit Datenquellen, einschließlich relationaler Datenbanken und XML\-Daten.  
  
 [XmlDataDocument\-Klasse](frlrfSystemXmlXmlDataDocumentClassTopic)  
 Enthält Referenzinformationen zur **XmlDataDocument**\-Klasse.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)