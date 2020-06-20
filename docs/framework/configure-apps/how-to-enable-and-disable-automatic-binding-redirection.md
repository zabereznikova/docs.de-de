---
title: Aktivieren oder Deaktivieren von automatisch generierten Bindungs Umleitungen
description: Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der automatischen Bindungs Umleitung. Diese Funktion wirkt sich auf Desktop-Apps und Web-Apps aus, die auf .NET 4.5.1
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: edee95f6c3b2c2d74c4f1b68e0a65e5cb0e85f54
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105387"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="df4dd-104">Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="df4dd-104">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="df4dd-105">Wenn Sie apps in Visual Studio kompilieren, die auf .NET Framework 4.5.1 und höhere Versionen ausgerichtet sind, können der APP-Konfigurationsdatei automatisch Bindungs Umleitungen hinzugefügt werden, um die Assemblyvereinheitlichung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="df4dd-105">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="df4dd-106">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="df4dd-106">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="df4dd-107">Die Funktion zur automatischen Bindungs Umleitung wirkt sich auf Desktop-Apps und Web-Apps aus, die auf die .NET Framework 4.5.1 oder eine höhere Version abzielen, obwohl das Verhalten für eine Web-App etwas abweicht.</span><span class="sxs-lookup"><span data-stu-id="df4dd-107">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="df4dd-108">Sie können die automatische Bindungs Umleitung aktivieren, wenn Sie über vorhandene apps verfügen, die auf frühere Versionen des .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie Bindungs Umleitungen manuell erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="df4dd-108">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="df4dd-109">Deaktivieren von automatischen Bindungs Umleitungen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="df4dd-109">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="df4dd-110">Automatische Bindungs Umleitungen sind standardmäßig für Windows-Desktop-Apps aktiviert, die auf .NET Framework 4.5.1 und höhere Versionen abzielen.</span><span class="sxs-lookup"><span data-stu-id="df4dd-110">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="df4dd-111">Die Bindungs Umleitungen werden der Ausgabe Konfigurationsdatei (**app.config**) bei der Kompilierung der app hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="df4dd-111">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="df4dd-112">Die Quell **app.config** Datei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="df4dd-112">The source **app.config** file is not modified.</span></span> <span data-ttu-id="df4dd-113">Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für die APP ändern oder ein Kontrollkästchen in den Eigenschaften des Projekts in Visual Studio deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="df4dd-113">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="df4dd-114">Durch Projekteigenschaften deaktivieren</span><span class="sxs-lookup"><span data-stu-id="df4dd-114">Disable through project properties</span></span>

<span data-ttu-id="df4dd-115">Wenn Sie über Visual Studio 2017 Version 15,7 oder höher verfügen, können Sie automatisch generierte Bindungs Umleitungen auf den Eigenschaften Seiten des Projekts problemlos deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="df4dd-115">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="df4dd-116">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-116">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="df4dd-117">Deaktivieren Sie auf der Seite **Anwendung** die Option **Bindungs Umleitungen automatisch generieren** .</span><span class="sxs-lookup"><span data-stu-id="df4dd-117">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="df4dd-118">Drücken Sie **STRG** + **S** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="df4dd-118">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="df4dd-119">Manuelles Deaktivieren in der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="df4dd-119">Disable manually in the project file</span></span>

1. <span data-ttu-id="df4dd-120">Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="df4dd-120">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="df4dd-121">Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="df4dd-122">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="df4dd-122">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="df4dd-123">Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-123">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="df4dd-124">Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-124">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="df4dd-125">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="df4dd-125">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="df4dd-126">Ändern Sie `true` in`false`:</span><span class="sxs-lookup"><span data-stu-id="df4dd-126">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="df4dd-127">Manuelles Aktivieren automatischer Bindungs Umleitungen</span><span class="sxs-lookup"><span data-stu-id="df4dd-127">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="df4dd-128">Sie können automatische Bindungs Umleitungen in vorhandenen apps aktivieren, die auf ältere Versionen der .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df4dd-128">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="df4dd-129">Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen, erhalten Sie wahrscheinlich eine Buildausgabe, die eine Neuzuordnung der Assemblys vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="df4dd-129">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="df4dd-130">Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="df4dd-130">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="df4dd-131">Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-131">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="df4dd-132">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="df4dd-132">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="df4dd-133">Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-133">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="df4dd-134">Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.</span><span class="sxs-lookup"><span data-stu-id="df4dd-134">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="df4dd-135">Fügen Sie der ersten Konfigurations Eigenschaften Gruppe (unter dem-Tag) das folgende-Element hinzu \<PropertyGroup> :</span><span class="sxs-lookup"><span data-stu-id="df4dd-135">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="df4dd-136">Im folgenden sehen Sie eine Beispiel Projektdatei, in der das Element eingefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="df4dd-136">The following shows an example project file with the element inserted:</span></span>

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

3. <span data-ttu-id="df4dd-137">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="df4dd-137">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="df4dd-138">Aktivieren von automatischen Bindungs Umleitungen in Web-Apps</span><span class="sxs-lookup"><span data-stu-id="df4dd-138">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="df4dd-139">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="df4dd-139">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="df4dd-140">Da die Quell Konfigurationsdatei (**web.config**) für Web-Apps geändert werden muss, werden die Bindungs Umleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="df4dd-140">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="df4dd-141">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="df4dd-141">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="df4dd-142">Da Sie immer aufgefordert werden, Bindungs Umleitungen hinzuzufügen, müssen Sie diese Funktion für eine Web-App nicht explizit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="df4dd-142">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="df4dd-143">So fügen Sie einer **web.config** Datei Bindungs Umleitungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="df4dd-143">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="df4dd-144">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="df4dd-144">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="df4dd-145">![Buildwarnung für Assemblyverweiskonflikte](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="df4dd-145">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="df4dd-146">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df4dd-146">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="df4dd-147">Doppelklicken Sie auf die Warnung, oder wählen Sie die Warnung, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="df4dd-147">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="df4dd-148">Ein Dialogfeld, in dem Sie die erforderlichen Bindungs Umleitungen automatisch zur Quell **web.config** Datei hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="df4dd-148">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="df4dd-149">![Dialogfeld der Berechtigung für die Bindungsumleitung](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="df4dd-149">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="df4dd-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df4dd-150">See also</span></span>

- [<span data-ttu-id="df4dd-151">\<bindingRedirect>-Element</span><span class="sxs-lookup"><span data-stu-id="df4dd-151">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="df4dd-152">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="df4dd-152">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
