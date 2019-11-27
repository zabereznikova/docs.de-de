---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330261"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="fe755-102">Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe755-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="fe755-103">Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen Ihrer benutzerdefinierten `My`-Namespace Erweiterungen mithilfe von Visual Studio-Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="fe755-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="fe755-104">Wenn Sie eine Projektvorlage erstellen, für die ihre `My` Erweiterungen ein wesentlicher Bestandteil des neuen Projekt Typs sind, können Sie den benutzerdefinierten `My` Erweiterungs Code beim Exportieren der Vorlage einfach mit dem Projekt einschließen.</span><span class="sxs-lookup"><span data-stu-id="fe755-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="fe755-105">Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter Gewusst [wie: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="fe755-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="fe755-106">Wenn sich die Erweiterung des benutzerdefinierten `My` in einer einzelnen Codedatei befindet, können Sie die Datei als Element Vorlage exportieren, die Benutzer zu beliebigen Visual Basic Projekttypen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="fe755-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="fe755-107">Anschließend können Sie die Element Vorlage anpassen, um zusätzliche Funktionen und das Verhalten für die benutzerdefinierte `My` Erweiterung in einem Visual Basic-Projekt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe755-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="fe755-108">Diese Funktionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fe755-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="fe755-109">Ermöglicht Benutzern das Verwalten Ihrer benutzerdefinierten `My` Erweiterung auf der Seite " **Meine Erweiterungen** " des Visual Basic Projekt-Designers.</span><span class="sxs-lookup"><span data-stu-id="fe755-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="fe755-110">Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="fe755-111">Ausblenden der Element Vorlage für `My` Erweiterungen im Dialogfeld **Element hinzufügen** , sodass Sie nicht in der Liste der Projekt Elemente enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fe755-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="fe755-112">In diesem Thema wird erläutert, wie Sie eine benutzerdefinierte `My` Erweiterung als ausgeblendete Element Vorlage Verpacken, die auf der Seite **Meine Erweiterungen** des Visual Basic Projekt-Designers verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe755-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="fe755-113">Die Erweiterung für benutzerdefinierte `My` kann auch automatisch hinzugefügt werden, wenn einem Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="fe755-114">Erstellen einer My-Namespace Erweiterung</span><span class="sxs-lookup"><span data-stu-id="fe755-114">Create a My namespace extension</span></span>

<span data-ttu-id="fe755-115">Der erste Schritt beim Erstellen eines Bereitstellungs Pakets für eine benutzerdefinierte `My` Erweiterung besteht darin, die Erweiterung als einzelne Codedatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe755-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="fe755-116">Ausführliche Informationen und Anleitungen zum Erstellen einer benutzerdefinierten `My` Erweiterung finden Sie unter [Erweitern des My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="fe755-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="fe755-117">Exportieren einer My-Namespace Erweiterung als Element Vorlage</span><span class="sxs-lookup"><span data-stu-id="fe755-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="fe755-118">Nachdem Sie eine Codedatei mit der Erweiterung für den `My`-Namespace erstellt haben, können Sie die Codedatei als Visual Studio-Element Vorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="fe755-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="fe755-119">Anweisungen zum Exportieren einer Datei als Visual Studio-Element Vorlage finden Sie unter Gewusst [wie: Erstellen von Element Vorlagen](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="fe755-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="fe755-120">Wenn die `My`-Namespace Erweiterung von einer bestimmten Assembly abhängig ist, können Sie die Element Vorlage so anpassen, dass Ihre `My`-Namespace Erweiterung automatisch installiert wird, wenn ein Verweis auf diese Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="fe755-121">Daher sollten Sie diesen Assemblyverweis ausschließen, wenn Sie die Codedatei als Visual Studio-Element Vorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="fe755-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="fe755-122">Anpassen der Element Vorlage</span><span class="sxs-lookup"><span data-stu-id="fe755-122">Customize the item template</span></span>

<span data-ttu-id="fe755-123">Sie können die Verwaltung der Element Vorlage auf der Seite **Meine Erweiterungen** des Visual Basic Projekt-Designers aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe755-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="fe755-124">Sie können auch aktivieren, dass die Element Vorlage automatisch hinzugefügt wird, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="fe755-125">Um diese Anpassungen zu aktivieren, fügen Sie der Vorlage eine neue Datei (CustomData-Datei) hinzu, und fügen Sie dann dem XML-Code in der VSTEMPLATE-Datei ein neues Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe755-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="fe755-126">Hinzufügen der CustomData-Datei</span><span class="sxs-lookup"><span data-stu-id="fe755-126">Add the CustomData file</span></span>

<span data-ttu-id="fe755-127">Die CustomData-Datei ist eine Textdatei mit der Dateinamenerweiterung. CustomData (der Dateiname kann auf einen beliebigen Wert festgelegt werden, der für Ihre Vorlage sinnvoll ist) und der XML enthält.</span><span class="sxs-lookup"><span data-stu-id="fe755-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="fe755-128">Der XML-Code in der Datei "CustomData" weist Visual Basic an, die `My` Erweiterung einzuschließen, wenn Benutzer die Seite " **Meine Erweiterungen** " des Visual Basic Projekt-Designers verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe755-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="fe755-129">Optional können Sie das <`AssemblyFullName>`-Attribut zu ihrer CustomData-Datei-XML-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe755-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="fe755-130">Dies weist Visual Basic an, automatisch Ihre benutzerdefinierte `My` Erweiterung zu installieren, wenn dem Projekt ein Verweis auf eine bestimmte Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="fe755-131">Sie können einen beliebigen Text-Editor oder XML-Editor verwenden, um die CustomData-Datei zu erstellen, und Sie dann dem komprimierten Ordner der Element Vorlage (ZIP-Datei) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe755-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="fe755-132">Der folgende XML-Code zeigt z. b. den Inhalt einer CustomData-Datei, die das Vorlagen Element dem Ordner "Meine Erweiterungen" eines Visual Basic Projekts hinzufügt, wenn dem Projekt ein Verweis auf die Assembly "Microsoft. VisualBasic. PowerPacks. vs. dll" hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fe755-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="fe755-133">Die CustomData-Datei enthält eine <`VBMyExtensionTemplate>`-Element, das über Attribute verfügt, wie in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe755-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="fe755-134">Attribut</span><span class="sxs-lookup"><span data-stu-id="fe755-134">Attribute</span></span>|<span data-ttu-id="fe755-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe755-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="fe755-136">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="fe755-136">Required.</span></span> <span data-ttu-id="fe755-137">Ein eindeutiger Bezeichner für die Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="fe755-137">A unique identifier for the extension.</span></span> <span data-ttu-id="fe755-138">Wenn die Erweiterung mit dieser ID dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert, ihn erneut hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe755-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="fe755-139">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="fe755-139">Required.</span></span> <span data-ttu-id="fe755-140">Eine Versionsnummer für die Element Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fe755-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="fe755-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="fe755-141">Optional.</span></span> <span data-ttu-id="fe755-142">Ein Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="fe755-142">An assembly name.</span></span> <span data-ttu-id="fe755-143">Wenn dem Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, die `My` Erweiterung aus dieser Element Vorlage hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe755-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="fe755-144">Fügen Sie der VSTEMPLATE-Datei das \<CustomDataSignature >-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe755-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="fe755-145">Um die Visual Studio-Element Vorlage als `My`-Namespace Erweiterung zu identifizieren, müssen Sie auch die VSTEMPLATE-Datei für die Element Vorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="fe755-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="fe755-146">Sie müssen dem `<TemplateData>`-Element ein `<CustomDataSignature>`-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe755-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="fe755-147">Das `<CustomDataSignature>`-Element muss den Text `Microsoft.VisualBasic.MyExtension`enthalten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe755-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="fe755-148">Dateien in einem komprimierten Ordner (ZIP-Datei) können nicht direkt geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fe755-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="fe755-149">Kopieren Sie die VSTEMPLATE-Datei aus dem komprimierten Ordner, ändern Sie Sie, und ersetzen Sie dann die VSTEMPLATE-Datei im komprimierten Ordner durch die aktualisierte Kopie.</span><span class="sxs-lookup"><span data-stu-id="fe755-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="fe755-150">Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, der das `<CustomDataSignature>`-Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe755-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a><span data-ttu-id="fe755-151">Installieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="fe755-151">Install the template</span></span>

<span data-ttu-id="fe755-152">Zum Installieren der Vorlage können Sie den komprimierten Ordner (*ZIP* -Datei) in den Ordner "Visual Basic Element Vorlagen" kopieren.</span><span class="sxs-lookup"><span data-stu-id="fe755-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="fe755-153">Standardmäßig befinden sich Benutzer Element Vorlagen in *%USERPROFILE%\Documents\Visual Studio \<Version\>\templates\itemtemplates\visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="fe755-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="fe755-154">Alternativ können Sie die Vorlage als Visual Studio-Installer Datei ( *. vsi*) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fe755-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe755-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe755-155">See also</span></span>

- [<span data-ttu-id="fe755-156">Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe755-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="fe755-157">Erweitern des Visual Basic-Anwendungsmodells</span><span class="sxs-lookup"><span data-stu-id="fe755-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="fe755-158">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="fe755-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="fe755-159">My-Erweiterungen-Seite im Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="fe755-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
