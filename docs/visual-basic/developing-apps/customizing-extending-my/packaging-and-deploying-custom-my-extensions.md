---
title: Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330261"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="d5535-102">Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5535-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="d5535-103">Visual Basic stellt eine einfache Möglichkeit für Sie zur Verfügung, Ihre benutzerdefinierten `My`-Namespaceerweiterungen bereitzustellen, indem Visual Studio-Vorlagen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5535-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="d5535-104">Wenn Sie eine Projektvorlage erstellen, für die Ihre `My`-Erweiterungen ein integraler Bestandteil des neuen Projekttyps sind, können Sie einfach Ihren benutzerdefinierten `My`-Erweiterungscode mit dem Projekt einschließen, wenn Sie die Vorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="d5535-105">Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).</span><span class="sxs-lookup"><span data-stu-id="d5535-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="d5535-106">Wenn sich Ihre benutzerdefinierte `My`-Erweiterung in einer einzelnen Codedatei befindet, können Sie die Datei als eine Elementvorlage exportieren, die Benutzer jedem beliebigen Visual Basic-Projekttyp hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d5535-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="d5535-107">Sie können die Elementvorlage dann anpassen, um in einem Visual Basic-Projekt zusätzliche Funktionen und weiteres Verhalten für Ihre benutzerdefinierte `My`-Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="d5535-108">Zu diesen Funktionen gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="d5535-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="d5535-109">Zulassen, dass Benutzer Ihre benutzerdefinierte `My`-Erweiterung auf der Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwalten</span><span class="sxs-lookup"><span data-stu-id="d5535-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="d5535-110">Automatisches Hinzufügen Ihrer benutzerdefinierten `My`-Erweiterung, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="d5535-111">Ausblenden der `My`-Erweiterungselementvorlage im **Element hinzufügen**-Dialogfeld, sodass sie nicht in der Liste der Projektelemente angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="d5535-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="d5535-112">In diesem Thema wird erläutert, wie eine benutzerdefinierte `My`-Erweiterung als ausgeblendete Elementvorlage gepackt werden kann, die über die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d5535-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d5535-113">Die benutzerdefinierte `My`-Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="d5535-114">Erstellen einer My-Namespaceerweiterung</span><span class="sxs-lookup"><span data-stu-id="d5535-114">Create a My namespace extension</span></span>

<span data-ttu-id="d5535-115">Der erste Schritt für die Erstellung eines Bereitstellungspakets für eine benutzerdefinierte `My`-Erweiterung ist das Erstellen der Erweiterung als einzelne Codedatei.</span><span class="sxs-lookup"><span data-stu-id="d5535-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="d5535-116">Details und eine Anleitung, wie Sie eine benutzerdefinierte `My`-Erweiterung erstellen, finden Sie unter [Erweitern des My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d5535-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="d5535-117">Exportieren einer My-Namespaceerweiterung als Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="d5535-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="d5535-118">Nachdem Sie eine Codedatei erstellt haben, die Ihre `My`-Namespaceerweiterung beinhaltet, können Sie die Codedatei als Visual Studio-Elementvorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="d5535-119">Eine Anleitung zum Exportieren einer Datei als Visual Studio-Elementvorlage finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen](/visualstudio/ide/how-to-create-item-templates).</span><span class="sxs-lookup"><span data-stu-id="d5535-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="d5535-120">Wenn Ihre `My`-Namespaceerweiterung eine Abhängigkeit von einer bestimmten Assembly aufweist, können Sie die Elementvorlage so anpassen, dass Ihre `My`-Namespaceerweiterung automatisch installiert wird, wenn ein Verweis auf diese Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="d5535-121">Dies hat zur Folge, dass Sie diesen Assemblyverweis ausschließen sollten, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="d5535-122">Anpassen der Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="d5535-122">Customize the item template</span></span>

<span data-ttu-id="d5535-123">Sie können aktivieren, dass Ihre Elementvorlage über die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d5535-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d5535-124">Sie können auch aktivieren, dass die Elementvorlage automatisch hinzugefügt wird, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="d5535-125">Wenn Sie diese Anpassungen aktivieren möchten, fügen Sie Ihrer Vorlage eine neue Datei hinzu, die als CustomData-Datei bezeichnet wird. Dann fügen Sie im XML-Code in Ihrer VSTEMPLATE-Datei ein neues Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5535-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="d5535-126">Hinzufügen der CustomData-Datei</span><span class="sxs-lookup"><span data-stu-id="d5535-126">Add the CustomData file</span></span>

<span data-ttu-id="d5535-127">Die CustomData-Datei ist eine Textdatei, die die Dateinamenserweiterung .CustomData aufweist und XML enthält. Der Dateiname kann auf einen beliebigen Wert festgelegt werden, der für Ihre Vorlage sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="d5535-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="d5535-128">Der XML-Code in der CustomData-Datei weist Visual Basic an, Ihre `My`-Erweiterung einzuschließen, wenn Benutzer die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5535-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d5535-129">Optional können Sie im XML-Code Ihrer CustomData-Datei das <`AssemblyFullName>`-Attribut hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5535-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="d5535-130">Dadurch wird Visual Basic angewiesen, automatisch Ihrer benutzerdefinierte `My`-Erweiterung zu installieren, wenn ein Verweis auf eine bestimmte Assembly dem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="d5535-131">Sie können einen beliebigen Text- oder XML-Editor verwenden, um die CustomData-Datei zu erstellen und sie dann dem komprimierten Ordner Ihrer Elementvorlage hinzufügen (ZIP-Datei).</span><span class="sxs-lookup"><span data-stu-id="d5535-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="d5535-132">Der folgende XML-Code zeigt beispielsweise die Inhalte einer CustomData-Datei, die die Elementvorlage dem Ordner „Meine Erweiterungen“ eines Visual Basic-Projekts hinzufügt, wenn ein Verweis auf die Microsoft.VisualBasic.PowerPacks.Vs.dll-Assembly dem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5535-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="d5535-133">Die CustomData-Datei enthält ein <`VBMyExtensionTemplate>`-Element, das Attribute wie in der folgenden Tabelle beschrieben aufweist.</span><span class="sxs-lookup"><span data-stu-id="d5535-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="d5535-134">Attribut</span><span class="sxs-lookup"><span data-stu-id="d5535-134">Attribute</span></span>|<span data-ttu-id="d5535-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5535-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="d5535-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5535-136">Required.</span></span> <span data-ttu-id="d5535-137">Ein eindeutiger Bezeichner für die Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="d5535-137">A unique identifier for the extension.</span></span> <span data-ttu-id="d5535-138">Wenn die Erweiterung, die diesen Bezeichner aufweist, bereits dem Projekt hinzugefügt wurde, wird der Benutzer nicht dazu aufgefordert, sie noch mal hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5535-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="d5535-139">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5535-139">Required.</span></span> <span data-ttu-id="d5535-140">Eine Versionsnummer für die Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="d5535-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="d5535-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d5535-141">Optional.</span></span> <span data-ttu-id="d5535-142">Ein Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="d5535-142">An assembly name.</span></span> <span data-ttu-id="d5535-143">Wenn ein Verweis auf diese Assembly dem Projekt hinzugefügt wird, wird der Benutzer aufgefordert, die `My`-Erweiterung aus dieser Elementvorlage hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5535-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="d5535-144">Hinzufügen des \<CustomDataSignature>-Elements zur VSTEMPLATE-Datei</span><span class="sxs-lookup"><span data-stu-id="d5535-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="d5535-145">Sie müssen auch die VSTEMPLATE-Datei für Ihre Elementvorlage anpassen, um Ihre Visual Studio-Elementvorlage als `My`-Namespaceerweiterung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="d5535-146">Sie müssen dem `<TemplateData>`-Element ein `<CustomDataSignature>`-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5535-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="d5535-147">Das `<CustomDataSignature>`-Element muss wie im folgenden Beispiel gezeigt den Text `Microsoft.VisualBasic.MyExtension` enthalten.</span><span class="sxs-lookup"><span data-stu-id="d5535-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="d5535-148">Sie können Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d5535-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="d5535-149">Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, sie ändern und die VSTEMPLATE-Datei im komprimierten Ordner dann durch die aktualisierte Kopie ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d5535-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="d5535-150">Im folgenden Beispiel sehen Sie die Inhalte einer VSTEMPLATE-Datei, der das `<CustomDataSignature>`-Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d5535-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

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

## <a name="install-the-template"></a><span data-ttu-id="d5535-151">Installieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="d5535-151">Install the template</span></span>

<span data-ttu-id="d5535-152">Zur Installation der Vorlage können Sie den komprimierten Ordner (die *ZIP*-Datei) in den Elementvorlagenordner in Visual Basic kopieren.</span><span class="sxs-lookup"><span data-stu-id="d5535-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="d5535-153">Standardmäßig befinden sich Benutzerelementvorlagen unter *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span><span class="sxs-lookup"><span data-stu-id="d5535-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="d5535-154">Alternativ können Sie die Vorlage als Visual Studio-Installerdatei ( *.vsi*) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d5535-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5535-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5535-155">See also</span></span>

- [<span data-ttu-id="d5535-156">Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5535-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="d5535-157">Erweitern des Visual Basic-Anwendungsmodells</span><span class="sxs-lookup"><span data-stu-id="d5535-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="d5535-158">Anpassen der verfügbaren Objekte in „My“</span><span class="sxs-lookup"><span data-stu-id="d5535-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="d5535-159">My-Erweiterungen-Seite im Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="d5535-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
