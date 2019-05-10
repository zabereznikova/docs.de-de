---
title: 'Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 9e80f41e05fb78b7a6c1ef9ce47ef611cfe3e57d
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910641"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="75615-102">Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien</span><span class="sxs-lookup"><span data-stu-id="75615-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="75615-103">Externe Zuordnungsdateien und von Ihnen geänderte .dbml-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="75615-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="75615-104">Dieses Thema enthält Visual Studio-Benutzer mit den Schritten zum Implementieren des Validierungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="75615-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="75615-105">So validieren Sie ein .dbml- oder eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="75615-105">To validate a .dbml or XML file</span></span>  
  
1. <span data-ttu-id="75615-106">Visual Studio **Datei** Startmenü **öffnen**, und klicken Sie dann auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="75615-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2. <span data-ttu-id="75615-107">In der **geöffnete Datei** Dialogfeld klicken Sie auf der DBML- oder XML-Zuordnungsdatei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="75615-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="75615-108">Die Datei wird geöffnet, der **XML-Editor**.</span><span class="sxs-lookup"><span data-stu-id="75615-108">The file opens in the **XML Editor**.</span></span>  
  
3. <span data-ttu-id="75615-109">Mit der rechten Maustaste im Fensters, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="75615-109">Right-click the window, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="75615-110">In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte für die **Schemas** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75615-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="75615-111">Die **XML-Schemas** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75615-111">The **XML Schemas** dialog box opens.</span></span>  
  
5. <span data-ttu-id="75615-112">Beachten Sie die entsprechende Schemadefinition für den Zweck.</span><span class="sxs-lookup"><span data-stu-id="75615-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    - <span data-ttu-id="75615-113">DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml-Datei.</span><span class="sxs-lookup"><span data-stu-id="75615-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="75615-114">Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75615-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    - <span data-ttu-id="75615-115">LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="75615-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="75615-116">Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="75615-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6. <span data-ttu-id="75615-117">In der **verwenden** Spalte mit der gewünschten Schema Definition-Zeile, klicken Sie im Dropdown-Menü zu öffnen, und klicken Sie auf **dieses Schema verwenden**.</span><span class="sxs-lookup"><span data-stu-id="75615-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="75615-118">Die Schemadefinitionsdatei ist nun der DBML- oder XML-Zuordnungsdatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="75615-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="75615-119">Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="75615-119">Make sure no other schema definitions are selected.</span></span>  
  
7. <span data-ttu-id="75615-120">Auf der **Ansicht** Menü klicken Sie auf **Fehlerliste**.</span><span class="sxs-lookup"><span data-stu-id="75615-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="75615-121">Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="75615-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="75615-122">Ist dies nicht der Fall, ist die XML-Datei für die Schemadefinition gültig.</span><span class="sxs-lookup"><span data-stu-id="75615-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="75615-123">Alternative Methode zur Bereitstellung einer Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="75615-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="75615-124">Wenn aus irgendeinem Grund die passende .xsd Datei nicht in angezeigt wird der **XML-Schemas** im Dialogfeld können Sie die XSD-Datei aus einem Hilfethema herunterladen.</span><span class="sxs-lookup"><span data-stu-id="75615-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="75615-125">Die folgenden Schritte können Sie die speichern Sie der heruntergeladenen Datei im Unicode-Format von XML-Editor von Visual Studio erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75615-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="75615-126">So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema</span><span class="sxs-lookup"><span data-stu-id="75615-126">To copy a schema definition file from a Help topic</span></span>  
  
1. <span data-ttu-id="75615-127">Suchen Sie das Hilfethema, das die Schemadefinition enthält (siehe weiter oben in diesem Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="75615-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    - <span data-ttu-id="75615-128">.Dbml-Dateien finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="75615-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    - <span data-ttu-id="75615-129">Externe Zuordnungsdateien finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="75615-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2. <span data-ttu-id="75615-130">Klicken Sie auf **Code kopieren** , die Codedatei in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="75615-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3. <span data-ttu-id="75615-131">Starten Sie Editor, um eine neue Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75615-131">Start Notepad to create a new file.</span></span>  
  
4. <span data-ttu-id="75615-132">Fügen Sie den Code aus der Zwischenablage in die Editor-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="75615-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5. <span data-ttu-id="75615-133">Klicken Sie im Editor **Datei** Menü klicken Sie auf **speichern**.</span><span class="sxs-lookup"><span data-stu-id="75615-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6. <span data-ttu-id="75615-134">In der **Codierung** Kontrollkästchen **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="75615-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="75615-135">Diese Auswahl stellt sicher, dass die Unicode-16-Byte-Sortierungsmarkierung (`FFFE`) der Textdatei vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="75615-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7. <span data-ttu-id="75615-136">In der **Dateiname** erstellen einen Dateinamen mit der Erweiterung XSD.</span><span class="sxs-lookup"><span data-stu-id="75615-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75615-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75615-137">See also</span></span>

- [<span data-ttu-id="75615-138">Verweis</span><span class="sxs-lookup"><span data-stu-id="75615-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
