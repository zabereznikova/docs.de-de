---
title: DataSet- und XmlDataDocument-Synchronisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 2790f0a9edd5bfde96683e00725dd04555379adf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153299"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>DataSet- und XmlDataDocument-Synchronisierung

Das ADO.NET-<xref:System.Data.DataSet> stellt Daten relational dar. Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML-Klassen verwenden. Diese beiden Datendarstellungen wurden bisher immer separat verwendet. Der-.NET Framework ermöglicht jedoch den synchronen Zugriff in Echtzeit auf die relationale und hierarchische Darstellung von Daten über das **DataSet** -Objekt <xref:System.Xml.XmlDataDocument> bzw. das-Objekt.  
  
 Wenn ein **DataSet** mit einem **xmldatadocumschlag**synchronisiert wird, arbeiten beide Objekte mit einem einzelnen Satz von Daten. Dies bedeutet Folgendes: Wenn eine Änderung am **DataSet**vorgenommen wird, wird die Änderung im **XmlDataDocument**reflektiert und umgekehrt. Die Beziehung zwischen dem **DataSet** und dem **xmldatadocreent** sorgt für eine hohe Flexibilität, indem eine einzelne Anwendung zugelassen wird. Verwenden eines einzelnen Satzes von Daten für den Zugriff auf die gesamte Sammlung von Diensten, die für das **DataSet** erstellt wurde (z. b. Web Forms-und Windows Forms-Steuerelemente und Visual Studio .NET-Designer), sowie die Auflistung von XML-Diensten, einschließlich Extensible Stylesheet Language (XSL), XSL-Transformationen (XSLT) und XPath (XML Path Language). Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.  
  
 Es gibt mehrere Möglichkeiten, wie Sie ein **DataSet** mit einem **xmldatadocumschlag**synchronisieren können. Ihre Möglichkeiten:  
  
- Füllen Sie ein **DataSet** mit einem Schema (d. h. einer relationalen Struktur) und Daten, und synchronisieren Sie es anschließend mit einem neuen **xmldatadocumschlag**. Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten. Zum Beispiel:  
  
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
  
- Füllen Sie ein **DataSet** nur mit einem Schema (z. b. einem **DataSet**mit starker Typisierung), synchronisieren Sie es mit einem **xmldatadocumschlag**, und laden Sie dann das **xmldatadocenent** aus einem XML-Dokument. Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten. Die Tabellennamen und Spaltennamen in Ihrem **DataSet** -Schema müssen mit den Namen der XML-Elemente identisch sein, mit denen Sie synchronisiert werden sollen. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
     Beachten Sie, dass das Schema des **DataSets** nur den XML-Elementen entsprechen muss, die Sie in ihrer relationalen Ansicht verfügbar machen möchten. Folglich können Sie ein sehr großes XML-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben. Das **xmldatadocreent** behält das gesamte XML-Dokument bei, obwohl das **DataSet** nur einen kleinen Teil davon verfügbar macht. (Ein ausführliches Beispiel hierfür finden Sie unter [Synchronisieren eines Datasets mit einem xmldatadocumschlag](synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     Im folgenden Codebeispiel werden die Schritte zum Erstellen eines **DataSets** und Auffüllen des Schemas sowie zum anschließenden Synchronisieren mit einem **xmldatadocumschlag**veranschaulicht. Beachten Sie, dass das **DataSet** -Schema nur mit den Elementen aus dem **xmldatadocreent** übereinstimmen muss, das Sie mithilfe des **DataSets**verfügbar machen möchten.  
  
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
  
     Ein **xmldatadocenent** kann nicht geladen werden, wenn es mit einem **DataSet** synchronisiert ist, das Daten enthält. In diesem Fall wird eine Ausnahme ausgelöst.  
  
- Erstellen Sie ein neues **xmldatadocumschlag** , und laden Sie es aus einem XML-Dokument. greifen Sie anschließend mithilfe der **DataSet** -Eigenschaft von **xmldatadocreent**auf die relationale Ansicht der Daten zu. Sie müssen das Schema des **DataSets** festlegen, bevor Sie die Daten im **xmldatadocumschlag** mithilfe des **DataSets**anzeigen können. Die Tabellennamen und Spaltennamen in Ihrem **DataSet** -Schema müssen mit den Namen der XML-Elemente, mit denen Sie synchronisiert werden sollen, identisch sein. Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.  
  
     Im folgenden Codebeispiel wird gezeigt, wie Sie auf die relationale Ansicht der Daten in einem **xmldatadocumschlag**zugreifen können.  
  
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
  
 Ein weiterer Vorteil der Synchronisierung eines **xmldatadocumschlag** mit einem **DataSet** besteht darin, dass die Genauigkeit eines XML-Dokuments beibehalten wird. Wenn das **DataSet** mithilfe von "read **XML**" aus einem XML-Dokument aufgefüllt wird und die Daten als XML-Dokument mit " **Write texml** " zurückgeschrieben werden, kann es sich erheblich vom ursprünglichen XML-Dokument unterscheiden. Dies liegt daran, dass das **DataSet** keine Formatierung, wie z. b. Leerzeichen, oder hierarchische Informationen (z. b. Element Reihenfolge) aus dem XML-Dokument verwaltet. Das **DataSet** enthält auch keine Elemente aus dem XML-Dokument, die ignoriert wurden, da Sie nicht mit dem Schema des **DataSets**identisch waren. Durch die Synchronisierung eines **xmldatadocenent** mit einem **DataSet** kann die Formatierung und hierarchische Elementstruktur des ursprünglichen XML-Dokuments im **xmldatadocenument**verwaltet werden, während das **DataSet** nur die Daten und Schema Informationen enthält, die für das **DataSet**geeignet sind.  
  
 Wenn Sie ein **DataSet** mit einem **xmldatadocumschlag**synchronisieren, können sich die Ergebnisse in Abhängigkeit davon unterscheiden, ob die <xref:System.Data.DataRelation> Objekte Nested sind oder nicht. Weitere Informationen finden Sie unter Schachteln von [DataRelations](nesting-datarelations.md)-Elementen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Synchronisieren eines "DataSet "mit einem "XmlDataDocument"](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Veranschaulicht das Synchronisieren eines stark typisierten **DataSets**mit minimalem Schema mit einem **xmldatadocumschlag**.  
  
 [Ausführen einer XPath-Abfrage für ein DataSet](performing-an-xpath-query-on-a-dataset.md)  
 Veranschaulicht die Ausführung einer XPath-Abfrage für den Inhalt eines **DataSets**.  
  
 [Anwenden einer XSLT-Transformation auf ein DataSet](applying-an-xslt-transform-to-a-dataset.md)  
 Veranschaulicht das Anwenden einer XSLT-Transformation auf den Inhalt eines **DataSets**.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)  
 Beschreibt, wie das **DataSet** mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines **DataSets** als XML-Daten.  
  
 [Verschachteln von "DataRelations"](nesting-datarelations.md)  
 Erläutert die Wichtigkeit von masted **DataRelations** -Objekten beim Darstellen des Inhalts eines **DataSets** als XML-Daten und beschreibt, wie diese Beziehungen erstellt werden.  
  
 ["DataSets", "DataTables" und "DataViews"](index.md)  
 Beschreibt das **DataSet** und dessen Verwendung zum Verwalten von Anwendungsdaten und zum interagieren mit Datenquellen, einschließlich relationaler Datenbanken und XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Enthält Referenzinformationen zur **xmldatadocenument** -Klasse.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
