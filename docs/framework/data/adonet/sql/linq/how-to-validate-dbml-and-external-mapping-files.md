---
title: "Gewusst wie: Überprüfen von DBML- und externen Zuordnungsdateien"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c4c17b41f9bee3ce43b7627343fec2b5a69dbba8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="fdb18-102">Gewusst wie: Überprüfen von DBML- und externen Zuordnungsdateien</span><span class="sxs-lookup"><span data-stu-id="fdb18-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="fdb18-103">Externe Zuordnungsdateien und von Ihnen geänderte .dbml-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="fdb18-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="fdb18-104">Dieser Abschnitt bietet [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Benutzern Informationen zu den Schritten für das Implementieren des Validierungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="fdb18-104">This topic provides [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="fdb18-105">So validieren Sie ein .dbml- oder eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="fdb18-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="fdb18-106">Visual Studio **Datei** Sie im Menü **öffnen**, und klicken Sie dann auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="fdb18-107">In der **Dateiöffnungsmodus** Dialogfeld klicken Sie auf der DBML- oder XML-Zuordnungsdatei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="fdb18-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="fdb18-108">Die Datei wird geöffnet, der **XML-Editor**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="fdb18-109">Mit der rechten Maustaste in des Fensters, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="fdb18-110">In der **Eigenschaften** Fenster, klicken Sie auf die Schaltfläche für die **Schemas** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fdb18-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="fdb18-111">Die **XML-Schemas** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fdb18-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="fdb18-112">Beachten Sie die entsprechende Schemadefinition für den Zweck.</span><span class="sxs-lookup"><span data-stu-id="fdb18-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="fdb18-113">DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml-Datei.</span><span class="sxs-lookup"><span data-stu-id="fdb18-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="fdb18-114">Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fdb18-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="fdb18-115">LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="fdb18-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="fdb18-116">Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="fdb18-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="fdb18-117">In der **verwenden** Spalte der gewünschten Schema Definition Zeile, klicken Sie zum Öffnen Sie das Dropdownfeld, und klicken Sie dann auf **dieses Schema verwenden**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="fdb18-118">Die Schemadefinitionsdatei ist nun der DBML- oder XML-Zuordnungsdatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fdb18-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="fdb18-119">Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="fdb18-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="fdb18-120">Auf der **Ansicht** Menü klicken Sie auf **Fehlerliste**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="fdb18-121">Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="fdb18-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="fdb18-122">Ist dies nicht der Fall, ist die XML-Datei für die Schemadefinition gültig.</span><span class="sxs-lookup"><span data-stu-id="fdb18-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="fdb18-123">Alternative Methode zur Bereitstellung einer Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="fdb18-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="fdb18-124">Wenn aus irgendeinem Grund die passende .xsd Datei nicht in angezeigt wird der **XML-Schemas** (Dialogfeld), können Sie die XSD-Datei aus einem Hilfethema herunterladen.</span><span class="sxs-lookup"><span data-stu-id="fdb18-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="fdb18-125">Die folgenden Schritte unterstützen Sie beim Speichern der heruntergeladenen Datei im Unicode-Format des [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-XML-Editors.</span><span class="sxs-lookup"><span data-stu-id="fdb18-125">The following steps help you save the downloaded file in the Unicode format required by the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="fdb18-126">So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema</span><span class="sxs-lookup"><span data-stu-id="fdb18-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="fdb18-127">Suchen Sie das Hilfethema, das die Schemadefinition enthält (siehe weiter oben in diesem Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="fdb18-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="fdb18-128">DBML-Dateien finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fdb18-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="fdb18-129">Externe Zuordnungsdateien finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="fdb18-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="fdb18-130">Klicken Sie auf **Code kopieren** auf die Codedatei in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="fdb18-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="fdb18-131">Starten Sie Editor, um eine neue Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdb18-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="fdb18-132">Fügen Sie den Code aus der Zwischenablage in die Editor-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="fdb18-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="fdb18-133">Klicken Sie im Editor **Datei** Menü klicken Sie auf **speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="fdb18-134">In der **Codierung** wählen Sie im **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="fdb18-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fdb18-135">Diese Auswahl stellt sicher, dass die Unicode-16-Byte-Sortierungsmarkierung (`FFFE`) der Textdatei vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fdb18-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="fdb18-136">In der **Dateiname** Feld, erstellen Sie einen Dateinamen mit der Erweiterung XSD.</span><span class="sxs-lookup"><span data-stu-id="fdb18-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb18-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdb18-137">See Also</span></span>  
 [<span data-ttu-id="fdb18-138">Referenz</span><span class="sxs-lookup"><span data-stu-id="fdb18-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
