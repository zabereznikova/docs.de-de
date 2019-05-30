---
title: Aktivieren oder Deaktivieren von automatisch generierten bindungsumleitungen
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: b6c9c3508c53e8a68a3f7e1cb12b6b6c95600e7b
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380103"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="0a369-102">Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="0a369-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="0a369-103">Beim Kompilieren von apps in Visual Studio mit der Zielversion .NET Framework 4.5.1 und höheren Versionen können bindungsumleitungen automatisch Assemblyvereinheitlichung überschrieben app-Konfigurationsdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0a369-103">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="0a369-104">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="0a369-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="0a369-105">Die automatische bindungsumleitung wirkt sich auf desktop-apps und Web-apps für .NET Framework 4.5.1 oder höher, obwohl das Verhalten für eine Web-app etwas anders ist.</span><span class="sxs-lookup"><span data-stu-id="0a369-105">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="0a369-106">Sie können die automatische bindungsumleitung aktivieren, wenn Sie vorhandene apps, die frühere Versionen von .NET Framework abzielen, oder Sie diese Funktion deaktivieren können, wenn Sie manuell bindungsumleitungen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a369-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="0a369-107">Deaktivieren Sie automatische bindungsumleitungen in desktop-apps</span><span class="sxs-lookup"><span data-stu-id="0a369-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="0a369-108">Automatische bindungsumleitungen sind standardmäßig für Windows desktop-apps aktiviert, die auf .NET Framework 4.5.1 und höheren Versionen abzielen.</span><span class="sxs-lookup"><span data-stu-id="0a369-108">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="0a369-109">Die bindungsumleitungen werden hinzugefügt, um die Ausgabekonfigurationsdatei ( **"App.config"** )-Datei, wenn die app kompiliert wurde, und überschreiben Sie die Assemblyvereinheitlichung, die sonst erfolgen würde.</span><span class="sxs-lookup"><span data-stu-id="0a369-109">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="0a369-110">Die Quelle **"App.config"** Datei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="0a369-110">The source **app.config** file is not modified.</span></span> <span data-ttu-id="0a369-111">Sie können dieses Feature deaktivieren, indem die Projektdatei für die app ändern oder deaktivieren ein Kontrollkästchen in den Eigenschaften des Projekts in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0a369-111">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="0a369-112">Deaktivieren Sie über Projekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="0a369-112">Disable through project properties</span></span>

<span data-ttu-id="0a369-113">Wenn Sie Visual Studio 2017 Version 15.7 oder höher verfügen, können Sie ganz einfach automatisch generierten bindungsumleitungen in den Eigenschaftenseiten des Projekts deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0a369-113">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="0a369-114">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="0a369-114">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="0a369-115">Auf der **Anwendung** Seite aus, deaktivieren Sie die **Automatisches Generieren von bindungsumleitungen** Option.</span><span class="sxs-lookup"><span data-stu-id="0a369-115">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="0a369-116">Drücken Sie **STRG**+**S** um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0a369-116">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="0a369-117">Deaktivieren Sie manuell in der Projektdatei</span><span class="sxs-lookup"><span data-stu-id="0a369-117">Disable manually in the project file</span></span>

1. <span data-ttu-id="0a369-118">Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="0a369-118">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="0a369-119">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0a369-119">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="0a369-120">Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="0a369-120">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="0a369-121">In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="0a369-121">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="0a369-122">Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]** .</span><span class="sxs-lookup"><span data-stu-id="0a369-122">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="0a369-123">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="0a369-123">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="0a369-124">Ändern Sie `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="0a369-124">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="0a369-125">Aktivieren Sie automatische bindungsumleitungen manuell</span><span class="sxs-lookup"><span data-stu-id="0a369-125">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="0a369-126">Sie können automatische bindungsumleitungen in vorhandenen apps ermöglichen dieses Ziel in älteren Versionen von .NET Framework oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, Hinzufügen einer Umleitung.</span><span class="sxs-lookup"><span data-stu-id="0a369-126">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="0a369-127">Wenn Sie eine neuere Version des Frameworks abzielen, jedoch werden nicht automatisch zum Hinzufügen einer Umleitung aufgefordert, erhalten Sie wahrscheinlich Buildausgabe, die schlägt vor, dass Sie die Assemblys neu zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0a369-127">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="0a369-128">Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="0a369-128">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="0a369-129">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0a369-129">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="0a369-130">Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="0a369-130">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="0a369-131">In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="0a369-131">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="0a369-132">Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]** .</span><span class="sxs-lookup"><span data-stu-id="0a369-132">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="0a369-133">Das folgende Element hinzufügen, um den ersten konfigurationseigenschaftengruppe (unter der \<PropertyGroup > Tag):</span><span class="sxs-lookup"><span data-stu-id="0a369-133">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="0a369-134">Das folgende Beispiel zeigt eine beispielhafte Projektdatei mit dem eingefügten Element:</span><span class="sxs-lookup"><span data-stu-id="0a369-134">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="0a369-135">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="0a369-135">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="0a369-136">Aktivieren Sie automatische bindungsumleitungen in Web-apps</span><span class="sxs-lookup"><span data-stu-id="0a369-136">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="0a369-137">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="0a369-137">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="0a369-138">Da der Quellkonfiguration ( **"Web.config"** ) Datei muss geändert werden, für die Web-apps, bindungsumleitungen werden nicht automatisch hinzugefügt, die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0a369-138">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="0a369-139">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="0a369-139">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="0a369-140">Da Sie immer zum Hinzufügen bindungsumleitungen aufgefordert werden, müssen Sie nicht explizit deaktivieren Sie dieses Feature für eine Web-app.</span><span class="sxs-lookup"><span data-stu-id="0a369-140">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="0a369-141">Zum Hinzufügen bindungsumleitungen zu einer **"Web.config"** Datei:</span><span class="sxs-lookup"><span data-stu-id="0a369-141">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="0a369-142">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="0a369-142">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="0a369-143">![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="0a369-143">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="0a369-144">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0a369-144">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="0a369-145">Doppelklicken Sie auf die Warnung aus, oder wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="0a369-145">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="0a369-146">Ein Dialogfeld, das Ihnen ermöglicht, automatisch die erforderlichen Bindung hinzuzufügen leitet an die Quelle **"Web.config"** -Datei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a369-146">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="0a369-147">![Dialogfeld "portbindung umleitungs-Berechtigung"](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="0a369-147">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="0a369-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a369-148">See also</span></span>

- [<span data-ttu-id="0a369-149">\<BindingRedirect >-Element</span><span class="sxs-lookup"><span data-stu-id="0a369-149">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="0a369-150">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="0a369-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
