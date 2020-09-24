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
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="9a239-102">DataSet- und XmlDataDocument-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="9a239-102">DataSet and XmlDataDocument Synchronization</span></span>

<span data-ttu-id="9a239-103">Das ADO.NET-<xref:System.Data.DataSet> stellt Daten relational dar.</span><span class="sxs-lookup"><span data-stu-id="9a239-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="9a239-104">Für einen hierarchischen Datenzugriff können Sie die in .NET Framework verfügbaren XML-Klassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a239-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="9a239-105">Diese beiden Datendarstellungen wurden bisher immer separat verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a239-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="9a239-106">Der-.NET Framework ermöglicht jedoch den synchronen Zugriff in Echtzeit auf die relationale und hierarchische Darstellung von Daten über das **DataSet** -Objekt <xref:System.Xml.XmlDataDocument> bzw. das-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9a239-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="9a239-107">Wenn ein **DataSet** mit einem **xmldatadocumschlag**synchronisiert wird, arbeiten beide Objekte mit einem einzelnen Satz von Daten.</span><span class="sxs-lookup"><span data-stu-id="9a239-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="9a239-108">Dies bedeutet Folgendes: Wenn eine Änderung am **DataSet**vorgenommen wird, wird die Änderung im **XmlDataDocument**reflektiert und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="9a239-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="9a239-109">Die Beziehung zwischen dem **DataSet** und dem **xmldatadocreent** sorgt für eine hohe Flexibilität, indem eine einzelne Anwendung zugelassen wird. Verwenden eines einzelnen Satzes von Daten für den Zugriff auf die gesamte Sammlung von Diensten, die für das **DataSet** erstellt wurde (z. b. Web Forms-und Windows Forms-Steuerelemente und Visual Studio .NET-Designer), sowie die Auflistung von XML-Diensten, einschließlich Extensible Stylesheet Language (XSL), XSL-Transformationen (XSLT) und XPath (XML Path Language).</span><span class="sxs-lookup"><span data-stu-id="9a239-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="9a239-110">Sie müssen nicht angeben, welche Gruppe von Diensten in Verbindung mit der Anwendung genutzt werden soll, da beide verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9a239-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="9a239-111">Es gibt mehrere Möglichkeiten, wie Sie ein **DataSet** mit einem **xmldatadocumschlag**synchronisieren können.</span><span class="sxs-lookup"><span data-stu-id="9a239-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="9a239-112">Ihre Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="9a239-112">You can:</span></span>  
  
- <span data-ttu-id="9a239-113">Füllen Sie ein **DataSet** mit einem Schema (d. h. einer relationalen Struktur) und Daten, und synchronisieren Sie es anschließend mit einem neuen **xmldatadocumschlag**.</span><span class="sxs-lookup"><span data-stu-id="9a239-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="9a239-114">Dadurch entsteht eine hierarchische Ansicht der vorhandenen relationalen Daten.</span><span class="sxs-lookup"><span data-stu-id="9a239-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="9a239-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9a239-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="9a239-116">Füllen Sie ein **DataSet** nur mit einem Schema (z. b. einem **DataSet**mit starker Typisierung), synchronisieren Sie es mit einem **xmldatadocumschlag**, und laden Sie dann das **xmldatadocenent** aus einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="9a239-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="9a239-117">Dadurch entsteht eine relationale Ansicht der vorhandenen hierarchischen Daten.</span><span class="sxs-lookup"><span data-stu-id="9a239-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="9a239-118">Die Tabellennamen und Spaltennamen in Ihrem **DataSet** -Schema müssen mit den Namen der XML-Elemente identisch sein, mit denen Sie synchronisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a239-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="9a239-119">Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="9a239-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="9a239-120">Beachten Sie, dass das Schema des **DataSets** nur den XML-Elementen entsprechen muss, die Sie in ihrer relationalen Ansicht verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9a239-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="9a239-121">Folglich können Sie ein sehr großes XML-Dokument und ein sehr kleines relationales "Fenster" für dieses Dokument haben.</span><span class="sxs-lookup"><span data-stu-id="9a239-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="9a239-122">Das **xmldatadocreent** behält das gesamte XML-Dokument bei, obwohl das **DataSet** nur einen kleinen Teil davon verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="9a239-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="9a239-123">(Ein ausführliches Beispiel hierfür finden Sie unter [Synchronisieren eines Datasets mit einem xmldatadocumschlag](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="9a239-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="9a239-124">Im folgenden Codebeispiel werden die Schritte zum Erstellen eines **DataSets** und Auffüllen des Schemas sowie zum anschließenden Synchronisieren mit einem **xmldatadocumschlag**veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a239-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="9a239-125">Beachten Sie, dass das **DataSet** -Schema nur mit den Elementen aus dem **xmldatadocreent** übereinstimmen muss, das Sie mithilfe des **DataSets**verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9a239-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="9a239-126">Ein **xmldatadocenent** kann nicht geladen werden, wenn es mit einem **DataSet** synchronisiert ist, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="9a239-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="9a239-127">In diesem Fall wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9a239-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="9a239-128">Erstellen Sie ein neues **xmldatadocumschlag** , und laden Sie es aus einem XML-Dokument. greifen Sie anschließend mithilfe der **DataSet** -Eigenschaft von **xmldatadocreent**auf die relationale Ansicht der Daten zu.</span><span class="sxs-lookup"><span data-stu-id="9a239-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="9a239-129">Sie müssen das Schema des **DataSets** festlegen, bevor Sie die Daten im **xmldatadocumschlag** mithilfe des **DataSets**anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9a239-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="9a239-130">Die Tabellennamen und Spaltennamen in Ihrem **DataSet** -Schema müssen mit den Namen der XML-Elemente, mit denen Sie synchronisiert werden sollen, identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9a239-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="9a239-131">Bei diesem Prozess wird die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="9a239-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="9a239-132">Im folgenden Codebeispiel wird gezeigt, wie Sie auf die relationale Ansicht der Daten in einem **xmldatadocumschlag**zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9a239-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="9a239-133">Ein weiterer Vorteil der Synchronisierung eines **xmldatadocumschlag** mit einem **DataSet** besteht darin, dass die Genauigkeit eines XML-Dokuments beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="9a239-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="9a239-134">Wenn das **DataSet** mithilfe von "read **XML**" aus einem XML-Dokument aufgefüllt wird und die Daten als XML-Dokument mit " **Write texml** " zurückgeschrieben werden, kann es sich erheblich vom ursprünglichen XML-Dokument unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9a239-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="9a239-135">Dies liegt daran, dass das **DataSet** keine Formatierung, wie z. b. Leerzeichen, oder hierarchische Informationen (z. b. Element Reihenfolge) aus dem XML-Dokument verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9a239-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="9a239-136">Das **DataSet** enthält auch keine Elemente aus dem XML-Dokument, die ignoriert wurden, da Sie nicht mit dem Schema des **DataSets**identisch waren.</span><span class="sxs-lookup"><span data-stu-id="9a239-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="9a239-137">Durch die Synchronisierung eines **xmldatadocenent** mit einem **DataSet** kann die Formatierung und hierarchische Elementstruktur des ursprünglichen XML-Dokuments im **xmldatadocenument**verwaltet werden, während das **DataSet** nur die Daten und Schema Informationen enthält, die für das **DataSet**geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="9a239-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="9a239-138">Wenn Sie ein **DataSet** mit einem **xmldatadocumschlag**synchronisieren, können sich die Ergebnisse in Abhängigkeit davon unterscheiden, ob die <xref:System.Data.DataRelation> Objekte Nested sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9a239-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="9a239-139">Weitere Informationen finden Sie unter Schachteln von [DataRelations](nesting-datarelations.md)-Elementen.</span><span class="sxs-lookup"><span data-stu-id="9a239-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a239-140">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9a239-140">In This Section</span></span>  

 [<span data-ttu-id="9a239-141">Synchronisieren eines "DataSet "mit einem "XmlDataDocument"</span><span class="sxs-lookup"><span data-stu-id="9a239-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="9a239-142">Veranschaulicht das Synchronisieren eines stark typisierten **DataSets**mit minimalem Schema mit einem **xmldatadocumschlag**.</span><span class="sxs-lookup"><span data-stu-id="9a239-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="9a239-143">Ausführen einer XPath-Abfrage für ein DataSet</span><span class="sxs-lookup"><span data-stu-id="9a239-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="9a239-144">Veranschaulicht die Ausführung einer XPath-Abfrage für den Inhalt eines **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="9a239-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="9a239-145">Anwenden einer XSLT-Transformation auf ein DataSet</span><span class="sxs-lookup"><span data-stu-id="9a239-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="9a239-146">Veranschaulicht das Anwenden einer XSLT-Transformation auf den Inhalt eines **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="9a239-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9a239-147">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9a239-147">Related Sections</span></span>  

 [<span data-ttu-id="9a239-148">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="9a239-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="9a239-149">Beschreibt, wie das **DataSet** mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines **DataSets** als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="9a239-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="9a239-150">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="9a239-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="9a239-151">Erläutert die Wichtigkeit von masted **DataRelations** -Objekten beim Darstellen des Inhalts eines **DataSets** als XML-Daten und beschreibt, wie diese Beziehungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9a239-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="9a239-152">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="9a239-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="9a239-153">Beschreibt das **DataSet** und dessen Verwendung zum Verwalten von Anwendungsdaten und zum interagieren mit Datenquellen, einschließlich relationaler Datenbanken und XML.</span><span class="sxs-lookup"><span data-stu-id="9a239-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="9a239-154">Enthält Referenzinformationen zur **xmldatadocenument** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="9a239-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a239-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a239-155">See also</span></span>

- [<span data-ttu-id="9a239-156">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9a239-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
