---
title: Aktivieren oder Deaktivieren von automatisch generierten Bindungs Umleitungen
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: 178d5070dd7018bbc0fce474cdd0b31ba3d17f77
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69913030"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="9c27f-102">Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="9c27f-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="9c27f-103">Wenn Sie apps in Visual Studio kompilieren, die auf .NET Framework 4.5.1 und höhere Versionen ausgerichtet sind, können der APP-Konfigurationsdatei automatisch Bindungs Umleitungen hinzugefügt werden, um die Assemblyvereinheitlichung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9c27f-103">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="9c27f-104">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="9c27f-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="9c27f-105">Die Funktion zur automatischen Bindungs Umleitung wirkt sich auf Desktop-Apps und Web-Apps aus, die auf die .NET Framework 4.5.1 oder eine höhere Version abzielen, obwohl das Verhalten für eine Web-App etwas abweicht.</span><span class="sxs-lookup"><span data-stu-id="9c27f-105">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="9c27f-106">Sie können die automatische Bindungs Umleitung aktivieren, wenn Sie über vorhandene apps verfügen, die auf frühere Versionen des .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie Bindungs Umleitungen manuell erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c27f-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="9c27f-107">Deaktivieren von automatischen Bindungs Umleitungen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="9c27f-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="9c27f-108">Automatische Bindungs Umleitungen sind standardmäßig für Windows-Desktop-Apps aktiviert, die auf .NET Framework 4.5.1 und höhere Versionen abzielen.</span><span class="sxs-lookup"><span data-stu-id="9c27f-108">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="9c27f-109">Die Bindungs Umleitungen werden der Ausgabe Konfigurationsdatei (**app. config**) hinzugefügt, wenn die APP kompiliert wird, und überschreiben die Assemblyvereinheitlichung, die andernfalls möglicherweise stattfindet.</span><span class="sxs-lookup"><span data-stu-id="9c27f-109">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="9c27f-110">Die Datei " **app. config** " der Quelldatei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="9c27f-110">The source **app.config** file is not modified.</span></span> <span data-ttu-id="9c27f-111">Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für die APP ändern oder ein Kontrollkästchen in den Eigenschaften des Projekts in Visual Studio deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c27f-111">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="9c27f-112">Durch Projekteigenschaften deaktivieren</span><span class="sxs-lookup"><span data-stu-id="9c27f-112">Disable through project properties</span></span>

<span data-ttu-id="9c27f-113">Wenn Sie über Visual Studio 2017 Version 15,7 oder höher verfügen, können Sie automatisch generierte Bindungs Umleitungen auf den Eigenschaften Seiten des Projekts problemlos deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c27f-113">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="9c27f-114">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-114">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="9c27f-115">Deaktivieren Sie auf der Seite **Anwendung** die Option **Bindungs Umleitungen automatisch generieren** .</span><span class="sxs-lookup"><span data-stu-id="9c27f-115">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="9c27f-116">Drücken Sie **STRG** + **S** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9c27f-116">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="9c27f-117">Manuelles Deaktivieren in der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="9c27f-117">Disable manually in the project file</span></span>

1. <span data-ttu-id="9c27f-118">Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="9c27f-118">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="9c27f-119">Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-119">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="9c27f-120">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="9c27f-120">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="9c27f-121">Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-121">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="9c27f-122">Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-122">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="9c27f-123">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="9c27f-123">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="9c27f-124">Ändern Sie `true` in`false`:</span><span class="sxs-lookup"><span data-stu-id="9c27f-124">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="9c27f-125">Manuelles Aktivieren automatischer Bindungs Umleitungen</span><span class="sxs-lookup"><span data-stu-id="9c27f-125">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="9c27f-126">Sie können automatische Bindungs Umleitungen in vorhandenen apps aktivieren, die auf ältere Versionen der .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9c27f-126">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="9c27f-127">Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen, erhalten Sie wahrscheinlich eine Buildausgabe, die eine Neuzuordnung der Assemblys vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="9c27f-127">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="9c27f-128">Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="9c27f-128">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="9c27f-129">Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-129">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="9c27f-130">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="9c27f-130">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="9c27f-131">Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-131">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="9c27f-132">Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.</span><span class="sxs-lookup"><span data-stu-id="9c27f-132">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="9c27f-133">Fügen Sie der ersten Konfigurations Eigenschaften Gruppe (unter dem-Tag) das folgende-Element hinzu \<PropertyGroup> :</span><span class="sxs-lookup"><span data-stu-id="9c27f-133">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="9c27f-134">Im folgenden sehen Sie eine Beispiel Projektdatei, in der das Element eingefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="9c27f-134">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="9c27f-135">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="9c27f-135">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="9c27f-136">Aktivieren von automatischen Bindungs Umleitungen in Web-Apps</span><span class="sxs-lookup"><span data-stu-id="9c27f-136">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="9c27f-137">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="9c27f-137">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="9c27f-138">Da die Quell Konfigurationsdatei (**Web. config**) für Web-Apps geändert werden muss, werden die Bindungs Umleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9c27f-138">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="9c27f-139">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="9c27f-139">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="9c27f-140">Da Sie immer aufgefordert werden, Bindungs Umleitungen hinzuzufügen, müssen Sie diese Funktion für eine Web-App nicht explizit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c27f-140">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="9c27f-141">So fügen Sie einer **Web. config** -Datei Bindungs Umleitungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="9c27f-141">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="9c27f-142">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="9c27f-142">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="9c27f-143">![Buildwarnung für Assemblyverweiskonflikte](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="9c27f-143">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="9c27f-144">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c27f-144">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="9c27f-145">Doppelklicken Sie auf die Warnung, oder wählen Sie die Warnung, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="9c27f-145">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="9c27f-146">Ein Dialogfeld, in dem Sie die erforderlichen Bindungs Umleitungen automatisch zur **Web. config** -Quelldatei hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9c27f-146">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="9c27f-147">![Dialogfeld der Berechtigung für die Bindungsumleitung](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="9c27f-147">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="9c27f-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c27f-148">See also</span></span>

- [<span data-ttu-id="9c27f-149">\<bindingRedirect>Gewisses</span><span class="sxs-lookup"><span data-stu-id="9c27f-149">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="9c27f-150">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="9c27f-150">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
