---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 81483722227873d1b145219ae5c4326d841ff876
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="0c7ad-102">Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c7ad-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="0c7ad-103">Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My` Namespaceerweiterungen mithilfe von Visual Studio-Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="0c7ad-104">Wenn Sie eine Projektvorlage für das Erstellen Ihrer `My` Erweiterungen sind ein wesentlicher Bestandteil des neuen Projekttyps, fügen Sie können Ihre benutzerdefinierten `My` Erweiterungscode mit dem Projekt, wenn Sie die Vorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="0c7ad-105">Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Gewusst wie: Erstellen von Projektvorlagen](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span><span class="sxs-lookup"><span data-stu-id="0c7ad-105">For more information about exporting project templates, see [How to: Create Project Templates](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span></span>  
  
 <span data-ttu-id="0c7ad-106">Wenn die benutzerdefinierte `My` -Erweiterung in einer einzelnen Codedatei befindet, können Sie die Datei exportieren, als eine Elementvorlage, die Benutzer auf jede Art von Visual Basic-Projekt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="0c7ad-107">Anschließend können Sie die Elementvorlage, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte Anpassen `My` -Erweiterung in einem Visual Basic-Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="0c7ad-108">Diese Funktionen sind unter anderem:</span><span class="sxs-lookup"><span data-stu-id="0c7ad-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="0c7ad-109">Ermöglicht Benutzern das Verwalten von benutzerdefinierten `My` -Erweiterung aus der **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="0c7ad-110">Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung, wenn ein Verweis auf eine angegebene Assembly zu einem Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="0c7ad-111">Ausblenden der `My` Erweiterung Item-Vorlage in die **hinzufügen** Dialogfeld, sodass es nicht in der Liste der Projektelemente enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="0c7ad-112">In diesem Thema erläutert, wie ein benutzerdefiniertes Paket `My` -Erweiterung als ausgeblendete Elementvorlage, die von verwaltet werden, kann die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0c7ad-113">Die benutzerdefinierte `My` Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="0c7ad-114">Erstellen einer My Namespaceerweiterung</span><span class="sxs-lookup"><span data-stu-id="0c7ad-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="0c7ad-115">Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My` -Erweiterung ist, die Erweiterung als einzelne Codedatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="0c7ad-116">Weitere Informationen und Anleitungen zum Erstellen eines benutzerdefinierten `My` -Erweiterung finden Sie unter [Erweitern der My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ad-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="0c7ad-117">Exportieren einer My Namespaceerweiterung als Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="0c7ad-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="0c7ad-118">Nachdem Sie eine Codedatei verfügen, enthält Ihre `My` Namespaceerweiterung können Sie die Codedatei als Visual Studio-Elementvorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="0c7ad-119">Informationen zum Exportieren einer Datei als Visual Studio-Elementvorlage finden Sie unter [Gewusst wie: Erstellen von Elementvorlagen](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span><span class="sxs-lookup"><span data-stu-id="0c7ad-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c7ad-120">Wenn Ihre `My` Namespaceerweiterung hat eine Abhängigkeit zu einer bestimmten Assembly, können Sie die Elementvorlage automatisch installiert, Anpassen Ihrer `My` Namespaceerweiterung, wenn ein Verweis auf diese Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="0c7ad-121">Daher sollten Sie der Assemblyverweis, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="0c7ad-122">Anpassen der Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="0c7ad-122">Customize the item template</span></span>  
 <span data-ttu-id="0c7ad-123">Sie können die Elementvorlage aus verwaltet werden die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0c7ad-124">Sie können auch festlegen, dass die Elementvorlage automatisch hinzugefügt werden soll, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="0c7ad-125">Um diese Anpassungen zu aktivieren, Sie fügen eine neue Datei mit dem Namen der CustomData-Datei und in der Vorlage aus, und dann ein neues Element in der XML in der VSTEMPLATE-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="0c7ad-126">Die CustomData-Datei hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0c7ad-126">Add the CustomData file</span></span>  
 <span data-ttu-id="0c7ad-127">Die CustomData-Datei ist eine Textdatei mit einer Erweiterung des Dateinamens. CustomData (der Dateiname kann festgelegt werden auf einen anderen Wert für die Vorlage), die XML enthält.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="0c7ad-128">Der XML-Code in der CustomData-Datei weist Visual Basic enthalten die `My` Erweiterung, wenn der Benutzer die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0c7ad-129">Sie können optional Hinzufügen der `AssemblyFullName>` der CustomData-Datei XML-Attribut.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="0c7ad-130">Dies weist Visual Basic automatisch installiert, die benutzerdefinierte `My` Erweiterung, wenn ein Verweis auf eine bestimmte Assembly wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="0c7ad-131">Sie können Text-Editor oder XML-Editor zum Erstellen der CustomData-Datei zu verwenden, und fügen Sie es in der Elementvorlage komprimierten Ordner (ZIP-Datei).</span><span class="sxs-lookup"><span data-stu-id="0c7ad-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="0c7ad-132">Die folgende XML-Code zeigt z. B. den Inhalt einer CustomData-Datei, die das Vorlagenelement in den Ordner My-Erweiterungen eine Visual Basic-Projekt, wenn Sie einen Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzufügen zum Projekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="0c7ad-133">Die CustomData-Datei enthält ein `VBMyExtensionTemplate>` -Element, das über die in der folgenden Tabelle aufgeführten Attribute verfügt.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="0c7ad-134">Attribut</span><span class="sxs-lookup"><span data-stu-id="0c7ad-134">Attribute</span></span>|<span data-ttu-id="0c7ad-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c7ad-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="0c7ad-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-136">Required.</span></span> <span data-ttu-id="0c7ad-137">Ein eindeutiger Bezeichner für die Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-137">A unique identifier for the extension.</span></span> <span data-ttu-id="0c7ad-138">Wenn die Erweiterung mit dieser ID dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert werden, wieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="0c7ad-139">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-139">Required.</span></span> <span data-ttu-id="0c7ad-140">Eine Versionsnummer für die Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="0c7ad-141">Optional.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-141">Optional.</span></span> <span data-ttu-id="0c7ad-142">Ein Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-142">An assembly name.</span></span> <span data-ttu-id="0c7ad-143">Wenn das Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, fügen die `My` Erweiterung aus dieser Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="0c7ad-144">Hinzufügen der \<CustomDataSignature > Element zur VSTEMPLATE-Datei</span><span class="sxs-lookup"><span data-stu-id="0c7ad-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="0c7ad-145">Identifizieren Sie die Visual Studio-Elementvorlage als eine `My` Namespaceerweiterung, müssen Sie auch die VSTEMPLATE-Datei für Ihre Elementvorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="0c7ad-146">Müssen Sie hinzufügen, eine `<CustomDataSignature>` Element, das `<TemplateData>` Element.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="0c7ad-147">Die `<CustomDataSignature>` Element muss den Text enthalten `Microsoft.VisualBasic.MyExtension`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="0c7ad-148">Sie können keine Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt ändern.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="0c7ad-149">Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, ändern, und ersetzen die VSTEMPLATE-Datei in einem komprimierten Ordner durch die aktualisierte Version.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="0c7ad-150">Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, die die `<CustomDataSignature>` Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
```  
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
  
## <a name="install-the-template"></a><span data-ttu-id="0c7ad-151">Installieren Sie die Vorlage</span><span class="sxs-lookup"><span data-stu-id="0c7ad-151">Install the template</span></span>  
 <span data-ttu-id="0c7ad-152">Um die Vorlage zu installieren, können Sie den komprimierten Ordner (ZIP-Datei) in den Visual Basic-Element-Vorlagen-Ordner (z. B. Eigene Dateien\Visual Studio 2008\Templates\Item Basic\Allgemein Basic) kopieren.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="0c7ad-153">Alternativ können Sie die Vorlage als Visual Studio-Installer (VSI)-Datei veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="0c7ad-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7ad-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c7ad-154">See also</span></span>  
 <span data-ttu-id="0c7ad-155">[Erweitern der meine Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="0c7ad-155">[Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span></span>  
<span data-ttu-id="0c7ad-156"> [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span><span class="sxs-lookup"><span data-stu-id="0c7ad-156"> [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span></span>  
<span data-ttu-id="0c7ad-157"> [Anpassen der-Objekte sind verfügbar für meine](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span><span class="sxs-lookup"><span data-stu-id="0c7ad-157"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span></span>  
<span data-ttu-id="0c7ad-158"> [Meine Erweiterungen-Seite, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="0c7ad-158"> [My Extensions Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>
