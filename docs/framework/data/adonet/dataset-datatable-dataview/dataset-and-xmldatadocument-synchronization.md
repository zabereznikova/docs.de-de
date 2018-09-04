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
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="e9b70-102">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="e9b70-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="e9b70-103">Das ADO.NET-<xref:System.Data.DataSet> stellt Daten relational dar.</span><span class="sxs-lookup"><span data-stu-id="e9b70-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="e9b70-104">Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML-Klassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9b70-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="e9b70-105">Diese beiden Datendarstellungen wurden bisher immer separat verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9b70-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="e9b70-106">Allerdings ermöglicht .NET Framework einen synchronen Echtzeitzugriff auf die relationale und hierarchische Darstellung von Daten mithilfe der **DataSet** Objekt und die <xref:System.Xml.XmlDataDocument> Zielabhängigkeitsobjekt.</span><span class="sxs-lookup"><span data-stu-id="e9b70-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="e9b70-107">Wenn eine **DataSet** mit synchronisiert eine **XmlDataDocument**, arbeiten beide Objekte mit einem einzigen Satz von Daten.</span><span class="sxs-lookup"><span data-stu-id="e9b70-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="e9b70-108">Dies bedeutet, dass eine Änderung vorgenommen wird, um die **DataSet**, die Änderung der **XmlDataDocument**, und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e9b70-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="e9b70-109">Die Beziehung zwischen der **DataSet** und **XmlDataDocument** erstellt Flexibilität durch eine einzelne Anwendung, die mit von einem einzigen Satz von Daten, auf die gesamte Suite von integrierten Dienste zugreifen können um die **DataSet** (z. B. Web Forms und Windows Forms-Steuerelemente und Designern für Visual Studio .NET) sowie die Sammlung von XML-Webdiensten, einschließlich Extensible Stylesheet Language (XSL), XSL Transformations (XSLT) und XML-Pfad Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="e9b70-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="e9b70-110">Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e9b70-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="e9b70-111">Es gibt mehrere Möglichkeiten, die Sie synchronisieren können eine **DataSet** mit einer **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="e9b70-112">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e9b70-112">You can:</span></span>  
  
-   <span data-ttu-id="e9b70-113">Auffüllen einer **DataSet** mit Schema (d. h. einer relationalen Struktur) und die Daten und synchronisieren sie mit einem neuen **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="e9b70-114">Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten.</span><span class="sxs-lookup"><span data-stu-id="e9b70-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="e9b70-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9b70-115">For example:</span></span>  
  
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
  
-   <span data-ttu-id="e9b70-116">Auffüllen einer **DataSet** Typ schema only (wie z. B. eine stark typisierte **DataSet**), synchronisieren sie mit eine **XmlDataDocument**, und Laden Sie die  **XmlDataDocument** aus einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="e9b70-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="e9b70-117">Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten.</span><span class="sxs-lookup"><span data-stu-id="e9b70-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="e9b70-118">Die Tabellen- und Spaltennamen müssen in Ihre **DataSet** Schema übereinstimmen die Namen der XML-Elemente, die Sie mit synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e9b70-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="e9b70-119">Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e9b70-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="e9b70-120">Beachten Sie, dass das Schema der **DataSet** muss nur die XML-Elemente übereinstimmen, die Sie in der relationalen Ansicht verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="e9b70-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="e9b70-121">Folglich können Sie ein sehr großes XML-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben.</span><span class="sxs-lookup"><span data-stu-id="e9b70-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="e9b70-122">Die **XmlDataDocument** behält Sie das gesamte XML-Dokument, obwohl die **DataSet** stellt nur einen kleinen Teil davon.</span><span class="sxs-lookup"><span data-stu-id="e9b70-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="e9b70-123">(Ein ausführliches Beispiel dieses finden Sie unter [Synchronisieren eines Datasets mit einem XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="e9b70-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="e9b70-124">Das folgende Codebeispiel zeigt die Schritte zum Erstellen einer **DataSet** und Füllen von dessen Schema sowie zum anschließenden Synchronisieren mit einem **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="e9b70-125">Beachten Sie, dass die **DataSet** Schema muss nur die Elemente entsprechend dem **XmlDataDocument** , die Sie verfügbar machen, verwenden möchten die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="e9b70-126">Sie können nicht geladen werden ein **XmlDataDocument** , wenn er mit synchronisiert wird eine **DataSet** , das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="e9b70-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="e9b70-127">In diesem Fall wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e9b70-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="e9b70-128">Erstellen Sie ein neues **XmlDataDocument** aus einem XML-Dokument laden, und klicken Sie dann Zugriff auf die relationale Ansicht der Daten mithilfe der **DataSet** Eigenschaft der **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="e9b70-129">Müssen Sie das Schema der Festlegen der **DataSet** , bevor Sie die Daten in anzeigen können die **XmlDataDocument** mithilfe der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="e9b70-130">In diesem Fall die Tabellen- und Spaltennamen im Namen Ihrer **DataSet** Schema übereinstimmen die Namen der XML-Elemente, die Sie mit synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e9b70-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="e9b70-131">Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e9b70-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="e9b70-132">Im folgenden Codebeispiel wird veranschaulicht, wie die relationale Ansicht der Daten in den Zugriff auf eine **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="e9b70-133">Ein weiterer Vorteil der Synchronisierung ein **XmlDataDocument** mit einem **DataSet** besteht darin, dass die Genauigkeit eines XML-Dokuments beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e9b70-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="e9b70-134">Wenn die **DataSet** wird aus einer XML-Dokument mit aufgefüllt **ReadXml**, wenn die Daten als XML-Dokument mit zurückgeschrieben werden **WriteXml** sie möglicherweise die unterscheiden sich erheblich, von der ursprüngliche XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="e9b70-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="e9b70-135">Grund hierfür ist die **DataSet** behält keine Formatierung, z. B. leer- oder hierarchische Informationen, wie die Reihenfolge der Elemente, aus dem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="e9b70-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="e9b70-136">Die **DataSet** auch keine Elemente aus dem XML-Dokument, das ignoriert wurden, da sie nicht das Schema der entspricht der **Dataset**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="e9b70-137">Synchronisieren einer **XmlDataDocument** mit einer **DataSet** ermöglicht die Formatierungen und die hierarchische Elementstruktur des ursprünglichen XML-Dokuments im beibehalten werden die **XmlDataDocument**, während die **DataSet** enthält nur Daten und Schema für die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="e9b70-138">Bei der Synchronisierung ein **DataSet** mit einer **XmlDataDocument**, Ergebnisse hängen davon ab, ob Ihre <xref:System.Data.DataRelation> -Objekte geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="e9b70-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="e9b70-139">Weitere Informationen finden Sie unter [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="e9b70-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9b70-140">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9b70-140">In This Section</span></span>  
 [<span data-ttu-id="e9b70-141">Synchronisieren eines DataSet mit einem XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="e9b70-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="e9b70-142">Demonstriert die Synchronisierung eine stark typisierte **DataSet**, mit dem Schema "minimal", mit einem **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="e9b70-143">Ausführen einer XPath-Abfrage für ein DataSet</span><span class="sxs-lookup"><span data-stu-id="e9b70-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="e9b70-144">Veranschaulicht die Ausführung einer XPath-Abfrage auf dem Inhalt einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="e9b70-145">Anwenden einer XSLT-Transformation auf ein DataSet</span><span class="sxs-lookup"><span data-stu-id="e9b70-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="e9b70-146">Veranschaulicht die Anwendung einer XSLT-Transformation auf den Inhalt einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e9b70-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9b70-147">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e9b70-147">Related Sections</span></span>  
 [<span data-ttu-id="e9b70-148">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="e9b70-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="e9b70-149">Beschreibt, wie die **DataSet** interagiert mit XML als Datenquelle, einschließlich des Ladens und Beibehaltens des Inhalts einer **DataSet** als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="e9b70-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="e9b70-150">Schachteln von DataRelations</span><span class="sxs-lookup"><span data-stu-id="e9b70-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="e9b70-151">Erläutert die Bedeutung geschachtelter **DataRelation** -Objekte beim Darstellen des Inhalts einer **DataSet** als XML-Daten, und beschreibt, wie diese Beziehungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9b70-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="e9b70-152">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="e9b70-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="e9b70-153">Beschreibt die **DataSet** und wie Sie es verwenden, um Anwendungsdaten zu verwalten und für die Interaktion mit Datenquellen, einschließlich relationaler Datenbanken und XML.</span><span class="sxs-lookup"><span data-stu-id="e9b70-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="e9b70-154">Enthält Referenzinformationen zu den **XmlDataDocument** Klasse.</span><span class="sxs-lookup"><span data-stu-id="e9b70-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b70-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9b70-155">See Also</span></span>  
 [<span data-ttu-id="e9b70-156">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e9b70-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
