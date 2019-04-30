---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014205"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="dc7c7-102">Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc7c7-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="dc7c7-103">Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My` Namespaceerweiterungen mithilfe von Visual Studio-Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="dc7c7-104">Wenn Sie eine Projektvorlage für das Erstellen Ihrer `My` Erweiterungen sind ein wesentlicher Bestandteil des neuen Projekttyps, Sie können nur einschließen, die benutzerdefinierte `My` Erweiterungscode mit dem Projekt aus, wenn Sie die Vorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="dc7c7-105">Weitere Informationen zum Exportieren von Vorlagen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="dc7c7-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="dc7c7-106">Wenn Ihre benutzerdefinierte `My` Erweiterung befindet sich in einer einzigen Codedatei, können Sie die Datei exportieren, wie eine Elementvorlage, die Benutzer auf jede Art von Visual Basic-Projekt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="dc7c7-107">Sie können dann die Item-Vorlage, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte Anpassen `My` -Erweiterung in Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="dc7c7-108">Diese Funktionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dc7c7-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="dc7c7-109">Ermöglicht Benutzern das Verwalten Ihrer benutzerdefiniertes `My` -Erweiterung aus der **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="dc7c7-110">Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine angegebene Assembly zu einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="dc7c7-111">Durch das Ausblenden der `My` Erweiterung Item-Vorlage in der **Element hinzufügen** Dialogfeld, sodass es nicht in der Liste der Projektelemente enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="dc7c7-112">In diesem Thema wird erläutert, wie Sie ein benutzerdefiniertes Paket `My` Erweiterung als ausgeblendetes Elementvorlage, die von verwaltet werden, kann die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="dc7c7-113">Die benutzerdefinierte `My` Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="dc7c7-114">Erstellen einer My-Namespaceerweiterung</span><span class="sxs-lookup"><span data-stu-id="dc7c7-114">Create a My namespace extension</span></span>

<span data-ttu-id="dc7c7-115">Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My` Erweiterung ist, um die Erweiterung als eine einzelne Codedatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="dc7c7-116">Weitere Informationen und Anleitungen zum Erstellen eines benutzerdefinierten `My` -Erweiterung finden Sie unter [erweitern die My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="dc7c7-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="dc7c7-117">Exportieren einer My-Namespaceerweiterung als eine Item-Vorlage</span><span class="sxs-lookup"><span data-stu-id="dc7c7-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="dc7c7-118">Nach dem Sie eine Codedatei, enthalten Ihre `My` Namespaceerweiterung, können Sie den Codedatei als Visual Studio-Elementvorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="dc7c7-119">Anweisungen dazu, wie Sie eine Datei als Visual Studio-Elementvorlage exportieren, finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="dc7c7-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="dc7c7-120">Wenn Ihre `My` Namespaceerweiterung besteht eine Abhängigkeit zu einer bestimmten Assembly, können Sie die Elementvorlage für die automatische Installation anpassen Ihrer `My` Namespaceerweiterung auf, wenn ein Verweis auf die Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="dc7c7-121">Daher werden Sie der Assemblyverweis, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="dc7c7-122">Die Item-Vorlage anpassen</span><span class="sxs-lookup"><span data-stu-id="dc7c7-122">Customize the item template</span></span>

<span data-ttu-id="dc7c7-123">Die Elementvorlage aus verwaltet werden können die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="dc7c7-124">Sie können auch ermöglichen, dass die Item-Vorlage automatisch hinzugefügt werden soll, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="dc7c7-125">Um diese Anpassungen zu aktivieren, Sie fügen eine neue Datei mit dem Namen der CustomData-Datei und in der Vorlage aus, und der XML-Code dann ein neues Element hinzugefügt werden, in der VSTEMPLATE-Datei.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="dc7c7-126">Die CustomData-Datei hinzufügen</span><span class="sxs-lookup"><span data-stu-id="dc7c7-126">Add the CustomData file</span></span>

<span data-ttu-id="dc7c7-127">Die CustomData-Datei ist eine Textdatei mit der Dateinamenerweiterung. CustomData (der Dateiname kann festgelegt werden auf einen beliebigen Wert für die Vorlage von Bedeutung), das XML enthält.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="dc7c7-128">Die XML-Code in die CustomData-Datei weist Visual Basic umfassen Ihre `My` Erweiterung auf, wenn der Benutzer die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="dc7c7-129">Sie können optional auch hinzufügen, die <`AssemblyFullName>` der CustomData-Datei XML-Attribut.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="dc7c7-130">Dies weist Visual Basic für die automatische Installation von benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine bestimmte Assembly wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="dc7c7-131">Sie können jeden beliebigen Text- oder XML-Editor verwenden, um die CustomData-Datei zu erstellen, und fügen Sie es auf der Elementvorlage komprimierten Ordner (ZIP-Datei).</span><span class="sxs-lookup"><span data-stu-id="dc7c7-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="dc7c7-132">Das folgende XML zeigt beispielsweise den Inhalt einer CustomData-Datei, die das Vorlagenelement in den Ordner My-Erweiterungen ein Visual Basic-Projekt, wenn ein Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzufügen wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="dc7c7-133">Die CustomData-Datei enthält ein <`VBMyExtensionTemplate>` -Element, das über in der folgenden Tabelle aufgeführten Attribute verfügt.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="dc7c7-134">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc7c7-134">Attribute</span></span>|<span data-ttu-id="dc7c7-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc7c7-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="dc7c7-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-136">Required.</span></span> <span data-ttu-id="dc7c7-137">Ein eindeutiger Bezeichner für die Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-137">A unique identifier for the extension.</span></span> <span data-ttu-id="dc7c7-138">Wenn die Erweiterung, die diese ID muss dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert werden, es erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="dc7c7-139">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-139">Required.</span></span> <span data-ttu-id="dc7c7-140">Eine Versionsnummer für die Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="dc7c7-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-141">Optional.</span></span> <span data-ttu-id="dc7c7-142">Ein Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-142">An assembly name.</span></span> <span data-ttu-id="dc7c7-143">Wenn das Projekt ein Verweis auf diese Assembly hinzugefügt wird, die Benutzer werden aufgefordert, Hinzufügen der `My` Erweiterung aus dieser Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="dc7c7-144">Hinzufügen der \<CustomDataSignature >-Element der VSTEMPLATE-Datei</span><span class="sxs-lookup"><span data-stu-id="dc7c7-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="dc7c7-145">Identifizieren Sie die Visual Studio-Elementvorlage als eine `My` Namespaceerweiterung, müssen Sie auch die VSTEMPLATE-Datei für die Item-Vorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="dc7c7-146">Müssen Sie hinzufügen, eine `<CustomDataSignature>` Element, das `<TemplateData>` Element.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="dc7c7-147">Die `<CustomDataSignature>` -Element muss den Text enthalten `Microsoft.VisualBasic.MyExtension`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="dc7c7-148">Sie können keine Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt ändern.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="dc7c7-149">Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, sie ändern und Ersetzen Sie die VSTEMPLATE-Datei in den komprimierten Ordner durch die aktualisierte Version.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="dc7c7-150">Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, die die `<CustomDataSignature>` hinzugefügte Element.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="dc7c7-151">Installieren Sie die Vorlage</span><span class="sxs-lookup"><span data-stu-id="dc7c7-151">Install the template</span></span>

<span data-ttu-id="dc7c7-152">Um die Vorlage zu installieren, können Sie den komprimierten Ordner kopieren (*ZIP* Datei) zum Ordner "Visual Basic Item Templates".</span><span class="sxs-lookup"><span data-stu-id="dc7c7-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="dc7c7-153">Standardmäßig befinden sich Benutzerelementvorlagen im *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="dc7c7-154">Alternativ können Sie die Vorlage als eine Visual Studio-Installer veröffentlichen (*VSI*) Datei.</span><span class="sxs-lookup"><span data-stu-id="dc7c7-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc7c7-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc7c7-155">See also</span></span>

- [<span data-ttu-id="dc7c7-156">Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc7c7-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="dc7c7-157">Erweitern des Visual Basic-Anwendungsmodells</span><span class="sxs-lookup"><span data-stu-id="dc7c7-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="dc7c7-158">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="dc7c7-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="dc7c7-159">My-Erweiterungen-Seite im Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="dc7c7-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
