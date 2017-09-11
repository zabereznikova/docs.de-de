---
title: 'Gewusst wie: Aktivieren von XML IntelliSense in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e367016c93586ad34492628b6a4384a5ef1b6acd
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="54693-102">Gewusst wie: Aktivieren von IntelliSense für XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54693-102">How to: Enable XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="54693-103">IntelliSense für XML in Visual Basic bietet wortvervollständigung für Elemente, die in einem XML-Schema definiert sind.</span><span class="sxs-lookup"><span data-stu-id="54693-103">XML IntelliSense in Visual Basic provides word completion for elements that are defined in an XML schema.</span></span> <span data-ttu-id="54693-104">Um IntelliSense für XML in Visual Basic zu aktivieren, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="54693-104">To enable XML IntelliSense in Visual Basic, you must do the following:</span></span>  
  
1.  <span data-ttu-id="54693-105">Rufen Sie die XML-Schemadatei (XSD) oder die Dateien für die XML-Dateien, die Ihre Anwendung lesen oder schreiben.</span><span class="sxs-lookup"><span data-stu-id="54693-105">Obtain the XML schema (XSD) file or files for the XML files that your application will read from or write to.</span></span>  
  
2.  <span data-ttu-id="54693-106">Schließen Sie die XML-Schemadateien in Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="54693-106">Include the XML schema files in your project.</span></span>  
  
3.  <span data-ttu-id="54693-107">Importieren Sie den Zielnamespace oder Namespaces in die Codedatei oder das Projekt.</span><span class="sxs-lookup"><span data-stu-id="54693-107">Import the target namespace or namespaces into your code file or project.</span></span> <span data-ttu-id="54693-108">Ein Zielnamespace wird anhand der `targetNamespace` oder `tns` -Attribut des XSD-Schemas.</span><span class="sxs-lookup"><span data-stu-id="54693-108">A target namespace is identified by the `targetNamespace` or `tns` attribute of your XSD schema.</span></span>  
  
     <span data-ttu-id="54693-109">Verwenden, um einen Zielnamespace Importieren der `Imports` -Anweisung, oder ein Namespace kann für alle Codedateien in einem Projekt hinzugefügt, mit der **Verweise** Seite im Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="54693-109">To import a target namespace, use the `Imports` statement, or add a namespace for all code files in a project by using the **References** page of the Project Designer.</span></span>  
  
 <span data-ttu-id="54693-110">Weitere Informationen über die Funktionen von IntelliSense für XML in Visual Basic finden Sie unter [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="54693-110">For more information on the capabilities of XML IntelliSense in Visual Basic, see [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span></span> <span data-ttu-id="54693-111">Weitere Informationen zum Importieren von XML-Namespaces finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) oder [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="54693-111">For more information on importing XML namespaces, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) or [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="54693-112">![Link zu Video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") eine Videoversion dieses Themas finden Sie unter [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span><span class="sxs-lookup"><span data-stu-id="54693-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For a video version of this topic, see [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span></span> <span data-ttu-id="54693-113">Eine entsprechende Videodemo finden Sie unter [Gewusst wie: Aktivieren von XML IntelliSense und Verwenden von XML-Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span><span class="sxs-lookup"><span data-stu-id="54693-113">For a related video demonstration, see [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span></span>  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="54693-114">Aktivieren von XML IntelliSense in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54693-114">Enable XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="54693-115">Wenn Sie eine XML-Datei verfügen, aber nicht über die XSD-Schemadatei verfügen, können in SP1 eine XSD-Schemadatei erstellen Sie mithilfe des XML-Schema-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="54693-115">If you have an XML file but you do not have an XSD schema file for it, in SP1 you can create an XSD schema file by using the XML to Schema Wizard.</span></span> <span data-ttu-id="54693-116">Sie können auch Schemarückschluss im XML-Editor von Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="54693-116">You can also use schema inference in the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a><span data-ttu-id="54693-117">Um eine XSD-Schemadatei für eine XML-Datei zu erstellen, mit dem XML-Schema-Assistenten erfordert (SP1)</span><span class="sxs-lookup"><span data-stu-id="54693-117">To create an XSD schema file for an XML file by using the XML to Schema Wizard (requires SP1)</span></span>  
  
1.  <span data-ttu-id="54693-118">Klicken Sie in Ihrem Projekt auf **neues Element hinzufügen** auf der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="54693-118">In your project, click **Add New Item** on the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="54693-119">Wählen Sie die **Xml zu Schema** Elementvorlage entweder aus der **Daten** oder **gemeinsame Elemente** Kategorien.</span><span class="sxs-lookup"><span data-stu-id="54693-119">Select the **Xml to Schema** item template from either the **Data** or **Common Items** template categories.</span></span>  
  
3.  <span data-ttu-id="54693-120">Geben Sie einen Namen für die XSD-Dateien, die das abgeleitete Schemaset gespeichert werden soll, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-120">Provide a file name for the XSD file or files that the inferred schema set will be stored in, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="54693-121">In der **XML-Schemaset aus XML-Dokumenten ableiten** Fenster, fügen Sie eine oder mehrere XML-Dokumente um das XML-Schemaset aus.</span><span class="sxs-lookup"><span data-stu-id="54693-121">In the **Infer XML Schema set from XML documents** window, add one or more XML documents to infer the XML schema set from.</span></span>  
  
    -   <span data-ttu-id="54693-122">Text-Dateien hinzufügen, die XML-Dokumente enthalten, mit dem Datei-Explorer, klicken Sie auf **aus Datei hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-122">To add text files that contain XML documents by using File Explorer, click **Add from File**.</span></span>  
  
    -   <span data-ttu-id="54693-123">Um ein XML-Dokument aus einer HTTP-Adresse hinzuzufügen, klicken Sie auf **aus Web hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-123">To add an XML document from an HTTP address, click **Add from Web**.</span></span>  
  
    -   <span data-ttu-id="54693-124">Zum Kopieren, oder geben Sie den Inhalt eines XML-Dokuments in den Assistenten, klicken Sie auf **XML eingeben oder einfügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-124">To copy or type the contents of an XML document into the wizard, click **Type or paste XML**.</span></span>  
  
5.  <span data-ttu-id="54693-125">Wenn Sie angegeben haben, alle XML-Dokument-Quellen, die zum Ableiten des XML-Schemasets auf soll **OK** legen Sie die XML-Schema abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="54693-125">When you have specified all the XML document sources from which you want to infer the XML schema set, click **OK** to infer the XML schema set.</span></span> <span data-ttu-id="54693-126">Das Schemaset wird im Projektordner in einer oder mehreren XSD-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="54693-126">The schema set is saved in your project folder in one or more XSD files.</span></span> <span data-ttu-id="54693-127">(Für jeden XML-Namespace im Schema wird eine Datei erstellt.)</span><span class="sxs-lookup"><span data-stu-id="54693-127">(For each XML namespace in the schema, a file is created.)</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a><span data-ttu-id="54693-128">So erstellen Sie eine XSD-Schemadatei für eine XML-Datei mit Schemarückschluss im XML-Editor von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="54693-128">To create an XSD schema file for an XML file by using schema inference in the Visual Studio XML Editor</span></span>  
  
1.  <span data-ttu-id="54693-129">Bearbeiten Sie die XML-Datei im XML-Designer von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="54693-129">Edit the XML file in the Visual Studio XML Designer.</span></span>  
  
2.  <span data-ttu-id="54693-130">Wenn der Cursor an einer beliebigen Stelle in der XML-Datei, die **XML** Menü wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54693-130">When the cursor is somewhere in the XML file, the **XML** menu appears.</span></span> <span data-ttu-id="54693-131">Klicken Sie auf **Create Schema** auf der **XML** Menü.</span><span class="sxs-lookup"><span data-stu-id="54693-131">Click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="54693-132">Eine XSD-Datei wird aus der XML-Datei abgeleiteten XSD-Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="54693-132">An XSD file is created from XSD schema inferred from the XML file.</span></span>  
  
3.  <span data-ttu-id="54693-133">Speichern Sie die XSD-Schemadatei.</span><span class="sxs-lookup"><span data-stu-id="54693-133">Save the XSD schema file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54693-134">Verschiedene XSD-Schemas können aus mehreren XML-Dokumenten abgeleitet werden, die das gleiche Schema aufweisen sollen.</span><span class="sxs-lookup"><span data-stu-id="54693-134">Different XSD schemas might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="54693-135">Dies kann auftreten, wenn bestimmte Elemente und Attribute in einer XML-Datei und nicht in einem anderen gefunden werden, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind, z. B..</span><span class="sxs-lookup"><span data-stu-id="54693-135">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="54693-136">Sie sollten die abgeleiteten XSD-Schemas auf Vollständigkeit und Genauigkeit bei der Verwendung von XSD-Schemarückschluss überprüfen.</span><span class="sxs-lookup"><span data-stu-id="54693-136">You should review inferred XSD schemas for completeness and accuracy when you use XSD schema inference.</span></span>  
  
#### <a name="to-include-an-xsd-schema-file"></a><span data-ttu-id="54693-137">Hinzufügen eine XSD-Schemadatei</span><span class="sxs-lookup"><span data-stu-id="54693-137">To include an XSD schema file</span></span>  
  
-   <span data-ttu-id="54693-138">In der Standardeinstellung nicht XSD-Dateien in Visual Basic-Projekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54693-138">By default, you cannot see XSD files in Visual Basic projects.</span></span> <span data-ttu-id="54693-139">Wenn die XSD-Datei bereits in den Ordnern für das Projekt enthalten ist, klicken Sie auf die **alle Dateien anzeigen** Schaltfläche **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="54693-139">If your XSD file is already included in the folders for your project, click the **Show All Files** button in **Solution Explorer**.</span></span> <span data-ttu-id="54693-140">Suchen Sie die XSD-Datei **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei, und klicken Sie auf **Datei in Projekt einschließen**.</span><span class="sxs-lookup"><span data-stu-id="54693-140">Locate the XSD file in **Solution Explorer**, right-click the file, and click **Include File in Project**.</span></span>  
  
-   <span data-ttu-id="54693-141">Ist die XSD-Datei nicht bereits Teil des Projekts, in **Projektmappen-Explorer**, mit der rechten Maustaste in des Ordners in dem Sie die XSD-Datei zu speichern, zeigen Sie auf möchten **hinzufügen**, und klicken Sie dann auf **vorhandenes Element**.</span><span class="sxs-lookup"><span data-stu-id="54693-141">If your XSD file is not already part of your project, in **Solution Explorer**, right-click the folder in which you want to store the XSD file, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="54693-142">Suchen Sie die XSD-Datei, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-142">Locate your XSD file and then click **Add**.</span></span>  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a><span data-ttu-id="54693-143">So importieren Sie einen XML-Namespace in eine Codedatei.</span><span class="sxs-lookup"><span data-stu-id="54693-143">To import an XML namespace in a code file</span></span>  
  
1.  <span data-ttu-id="54693-144">Identifizieren Sie den Zielnamespace des XSD-Schemas.</span><span class="sxs-lookup"><span data-stu-id="54693-144">Identify the target namespace from your XSD schema.</span></span>  
  
2.  <span data-ttu-id="54693-145">Fügen Sie am Anfang der Codedatei eine `Imports` -Anweisung für den XML-Zielnamespace, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="54693-145">At the beginning of the code file, add an `Imports` statement for the target XML namespace, as shown in the following example.</span></span>  
  
     <span data-ttu-id="54693-146">[!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="54693-146">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span></span>  
  
     <span data-ttu-id="54693-147">Um ein XML-Namespace als Standardnamespace zu importieren, d. h. der Namespace, der angewendet wird, um XML-Elemente und Attribute, die nicht über ein Namespacepräfix verfügen Hinzufügen einer `Imports` -Anweisung für den standardmäßigen XML-Zielnamespace.</span><span class="sxs-lookup"><span data-stu-id="54693-147">To import an XML namespace as the default namespace, that is, the namespace that is applied to XML elements and attributes that do not have a namespace prefix, add an `Imports` statement for the target default XML namespace.</span></span> <span data-ttu-id="54693-148">Geben Sie ein Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="54693-148">Do not specify a namespace prefix.</span></span> <span data-ttu-id="54693-149">Es folgt ein Beispiel für eine `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="54693-149">Following is an example of an `Imports` statement.</span></span>  
  
     <span data-ttu-id="54693-150">[!code-vb[VbXmlSamples&#50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="54693-150">[!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span></span>  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a><span data-ttu-id="54693-151">So importieren Sie einen XML-Namespace für alle Dateien in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="54693-151">To import an XML namespace for all files in a project</span></span>  
  
1.  <span data-ttu-id="54693-152">Ein XML-Namespace importiert wird, in einer Codedatei gilt nur für diese Codedatei.</span><span class="sxs-lookup"><span data-stu-id="54693-152">An XML namespace imported in a code file applies to that code file only.</span></span> <span data-ttu-id="54693-153">Um ein XML-Namespace zu importieren, die für alle Codedateien in einem Projekt gilt, öffnen Sie den Projekt-Designer durch Doppelklicken auf **Mein Projekt** in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="54693-153">To import an XML namespace that applies to all code files in a project, open the Project Designer by double-clicking **My Project** in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="54693-154">Auf der **Verweise** Registerkarte der **importierte Namespaces** Geben Sie den XML-Zielnamespace in Form einer vollständigen XML-Namespacedeklaration (z. B. `<xmlns: ns="http://sampleNamespace">`).</span><span class="sxs-lookup"><span data-stu-id="54693-154">On the **References** tab, in the **Imported namespaces** box, type the target XML namespace in the form of a full XML namespace declaration (for example, `<xmlns: ns="http://sampleNamespace">`).</span></span> <span data-ttu-id="54693-155">Wenn Sie der XML-Zielnamespace kein Namespace-Präfix angegeben ist, wird der Namespace der XML-Standardnamespace für das Projekt sein.</span><span class="sxs-lookup"><span data-stu-id="54693-155">If the target XML namespace does not specify a namespace prefix, the namespace will be the default XML namespace for the project.</span></span>  
  
3.  <span data-ttu-id="54693-156">Klicken Sie auf **Benutzerimport hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54693-156">Click **Add User Import**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54693-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54693-157">See Also</span></span>  
 <span data-ttu-id="54693-158">[Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="54693-158">[Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="54693-159"> [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="54693-159"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="54693-160"> [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span><span class="sxs-lookup"><span data-stu-id="54693-160"> [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span></span>

