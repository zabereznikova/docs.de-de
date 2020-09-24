---
title: Typische Schritte bei der Verwendung von LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: dc8c4be1e895ee5c4c7947e6311e5bf71008490f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164259"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="ce10f-102">Typische Schritte bei der Verwendung von LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ce10f-102">Typical Steps for Using LINQ to SQL</span></span>

<span data-ttu-id="ce10f-103">Zur Implementierung einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendung führen Sie die weiter unten beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ce10f-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="ce10f-104">Beachten Sie, dass viele Schritte optional sind.</span><span class="sxs-lookup"><span data-stu-id="ce10f-104">Note that many steps are optional.</span></span> <span data-ttu-id="ce10f-105">Es ist gut möglich, dass Sie das Objektmodell in seinem Standardzustand verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ce10f-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="ce10f-106">Verwenden Sie für einen schnellen Start die objektrelationaler Designer, um das Objektmodell zu erstellen und mit dem Codieren Ihrer Abfragen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-106">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="ce10f-107">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="ce10f-107">Creating the Object Model</span></span>  

 <span data-ttu-id="ce10f-108">Der erste Schritt besteht in der Erstellung eines Objektmodells aus den Metadaten einer vorhandenen relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ce10f-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="ce10f-109">Das Objektmodell stellt die Datenbank nach der Programmiersprache des Entwicklers dar.</span><span class="sxs-lookup"><span data-stu-id="ce10f-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="ce10f-110">Weitere Informationen finden Sie [unter LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-110">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="ce10f-111">1. Wählen Sie ein Tool aus, um das Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-111">1. Select a tool to create the model.</span></span>  

 <span data-ttu-id="ce10f-112">Für die Erstellung des Modells stehen drei Tools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ce10f-112">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="ce10f-113">Der objektrelationaler Designer</span><span class="sxs-lookup"><span data-stu-id="ce10f-113">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="ce10f-114">Dieser Designer stellt eine umfangreiche Benutzeroberfläche zum Erstellen eines Objektmodells aus einer vorhandenen Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="ce10f-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="ce10f-115">Dieses Tool ist Teil der Visual Studio-IDE und eignet sich am besten für kleine oder mittlere Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ce10f-115">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="ce10f-116">Das SQLMetal-Tool zur Codeerstellung</span><span class="sxs-lookup"><span data-stu-id="ce10f-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="ce10f-117">Dieses Befehlszeilen-Hilfsprogramm bietet eine etwas andere Gruppe von Optionen aus dem O/R-Designer.</span><span class="sxs-lookup"><span data-stu-id="ce10f-117">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="ce10f-118">Dieses Tool eignet sich vor allem für die Modellierung großer Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ce10f-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="ce10f-119">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="ce10f-120">Ein Code-Editor</span><span class="sxs-lookup"><span data-stu-id="ce10f-120">A code editor</span></span>  
  
     <span data-ttu-id="ce10f-121">Sie können eigenen Code schreiben, indem Sie entweder den Visual Studio Code-Editor oder einen anderen Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce10f-121">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="ce10f-122">Diese Vorgehensweise wird nicht empfohlen, da Sie fehleranfällig sein kann, wenn Sie über eine vorhandene Datenbank verfügen und entweder den O/R-Designer oder das SQLMetal-Tool verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ce10f-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="ce10f-123">Der Code-Editor kann sich jedoch beim Verfeinern und Ändern von bereits erzeugtem Code als nützlich erweisen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="ce10f-124">Weitere Informationen finden Sie unter Gewusst [wie: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="ce10f-125">2. Wählen Sie die Art des Codes aus, den Sie generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ce10f-125">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="ce10f-126">Eine c#-oder Visual Basic Quell Code Datei für die Attribut basierte Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ce10f-126">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="ce10f-127">Dann fügen Sie diese Codedatei in das Visual Studio-Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="ce10f-127">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="ce10f-128">Weitere Informationen finden Sie unter [Attribut basierte Zuordnung](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-128">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="ce10f-129">Eine XML-Datei für externe Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ce10f-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="ce10f-130">Sie können bei diesem Ansatz die Zuordnungsmetadaten vom Anwendungscode fernhalten.</span><span class="sxs-lookup"><span data-stu-id="ce10f-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="ce10f-131">Weitere Informationen finden Sie unter [externe Zuordnung](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-131">For more information, see [External Mapping](external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ce10f-132">Der O/R-Designer unterstützt die Generierung externer Mapping-Dateien nicht.</span><span class="sxs-lookup"><span data-stu-id="ce10f-132">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="ce10f-133">Sie müssen das SQLMetal-Tool verwenden, um diese Funktion zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce10f-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="ce10f-134">Eine DBML-Datei, die Sie vor dem Erzeugen einer abschließenden Codedatei ändern können.</span><span class="sxs-lookup"><span data-stu-id="ce10f-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="ce10f-135">Dies ist eine erweiterte Funktion.</span><span class="sxs-lookup"><span data-stu-id="ce10f-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="ce10f-136">3. verfeinern Sie die Codedatei, um die Anforderungen Ihrer Anwendung widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="ce10f-136">3. Refine the code file to reflect the needs of your application.</span></span>  

 <span data-ttu-id="ce10f-137">Zu diesem Zweck können Sie entweder den O/R-Designer oder den Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce10f-137">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="ce10f-138">Verwenden des Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="ce10f-138">Using the Object Model</span></span>  

 <span data-ttu-id="ce10f-139">Die folgende Abbildung zeigt die Beziehung zwischen dem Entwickler und den Daten in einem Szenario mit zwei Ebenen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="ce10f-140">Weitere Szenarios finden Sie unter [N-Tier-und Remote Anwendungen mit LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![Screenshot, der das LINQ-Objektmodell zeigt.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="ce10f-142">Mit dem gewählten Objektmodell beschreiben Sie Informationsanforderungen und bearbeiten Daten innerhalb des Modells.</span><span class="sxs-lookup"><span data-stu-id="ce10f-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="ce10f-143">Bei Ihrem Objektmodell geht es um Objekte und Eigenschaften, nicht um die Zeilen und Spalten der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ce10f-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="ce10f-144">Sie beschäftigen sich nicht direkt mit der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ce10f-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="ce10f-145">Wenn Sie anweisen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Abfrage auszuführen, die Sie für die von Ihnen bearbeiteten Daten beschrieben oder aufgerufen haben `SubmitChanges()` , [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kommuniziert mit der Datenbank in der Sprache der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ce10f-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="ce10f-146">Es folgen die typischen Schritte zum Verwenden des von Ihnen erstellen Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="ce10f-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="ce10f-147">1. Erstellen Sie Abfragen, um Informationen aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-147">1. Create queries to retrieve information from the database.</span></span>  

 <span data-ttu-id="ce10f-148">Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md) und [Abfrage Beispiele](query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-148">For more information, see [Query Concepts](query-concepts.md) and [Query Examples](query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="ce10f-149">2. überschreiben Sie das Standardverhalten für INSERT, Update und DELETE.</span><span class="sxs-lookup"><span data-stu-id="ce10f-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  

 <span data-ttu-id="ce10f-150">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="ce10f-150">This step is optional.</span></span> <span data-ttu-id="ce10f-151">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-151">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="ce10f-152">3. Legen Sie geeignete Optionen fest, um Parallelitäts Konflikte zu erkennen und zu melden.</span><span class="sxs-lookup"><span data-stu-id="ce10f-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  

 <span data-ttu-id="ce10f-153">Sie können Ihr Modell im Standardzustand belassen, um Parallelitätskonflikte zu beheben. Sie können das Modell auch ändern, um es an Ihre Zwecke anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ce10f-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="ce10f-154">Weitere Informationen finden Sie unter Gewusst [wie: angeben, welche Member auf Parallelitäts Konflikte getestet werden](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) und Gewusst [wie: angeben, wann](how-to-specify-when-concurrency-exceptions-are-thrown.md)Parallelitäts Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ce10f-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="ce10f-155">4. Erstellen Sie eine Vererbungs Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="ce10f-155">4. Establish an inheritance hierarchy.</span></span>  

 <span data-ttu-id="ce10f-156">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="ce10f-156">This step is optional.</span></span> <span data-ttu-id="ce10f-157">Weitere Informationen finden Sie [unter Vererbungs Unterstützung](inheritance-support.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-157">For more information, see [Inheritance Support](inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="ce10f-158">5. Stellen Sie eine entsprechende Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="ce10f-158">5. Provide an appropriate user interface.</span></span>  

 <span data-ttu-id="ce10f-159">Dieser Schritt ist optional und hängt davon ab, wie die Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce10f-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="ce10f-160">6. Debuggen und testen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ce10f-160">6. Debug and test your application.</span></span>  

 <span data-ttu-id="ce10f-161">Weitere Informationen finden Sie [unter Debuggingunterstützung](debugging-support.md).</span><span class="sxs-lookup"><span data-stu-id="ce10f-161">For more information, see [Debugging Support](debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce10f-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce10f-162">See also</span></span>

- [<span data-ttu-id="ce10f-163">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="ce10f-163">Getting Started</span></span>](getting-started.md)
- [<span data-ttu-id="ce10f-164">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="ce10f-164">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="ce10f-165">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ce10f-165">Stored Procedures</span></span>](stored-procedures.md)
