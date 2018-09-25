---
title: 'Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung'
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079542"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="b3c5c-102">Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="b3c5c-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="b3c5c-103">Beim Kompilieren von apps in Visual Studio, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und höhere Versionen werden bindungsumleitungen werden automatisch hinzugefügt, um die app-Konfigurationsdatei für die Assemblyvereinheitlichung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="b3c5c-104">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="b3c5c-105">Die automatische bindungsumleitung wirkt sich auf herkömmliche desktop-apps und Web-apps, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] oder eine höhere Version, obwohl das Verhalten für eine Web-app etwas anders ist.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="b3c5c-106">Sie können die automatische Bindungsumleitung aktivieren, wenn Sie über Apps verfügen, die auf frühere Versionen von .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie manuell erstellte Bindungsumleitungen beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="b3c5c-107">Deaktivieren Sie automatische bindungsumleitungen in desktop-apps</span><span class="sxs-lookup"><span data-stu-id="b3c5c-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="b3c5c-108">Automatische Bindungsumleitungen sind bei herkömmlichen Desktop-Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und spätere Versionen abzielen, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="b3c5c-109">Die Bindungsumleitungen werden der Ausgabekonfigurationsdatei (app.config) beim Kompilieren der App hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben, die sonst erfolgen würde.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="b3c5c-110">Die app.config-Quelldatei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-110">The source app.config file is not modified.</span></span> <span data-ttu-id="b3c5c-111">Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für Ihre App ändern.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-111">You can disable this feature by modifying the project file for the app.</span></span>

1. <span data-ttu-id="b3c5c-112">Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-112">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="b3c5c-113">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="b3c5c-114">Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-114">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="b3c5c-115">In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-115">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="b3c5c-116">Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-116">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="b3c5c-117">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-117">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="b3c5c-118">Ändern Sie `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-118">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="b3c5c-119">Aktivieren Sie automatische bindungsumleitungen manuell</span><span class="sxs-lookup"><span data-stu-id="b3c5c-119">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="b3c5c-120">Sie können automatische bindungsumleitungen in vorhandenen apps ermöglichen dieses Ziel in älteren Versionen von .NET Framework oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, Hinzufügen einer Umleitung.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-120">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="b3c5c-121">Wenn Sie eine neuere Version des Frameworks abzielen, jedoch werden nicht automatisch zum Hinzufügen einer Umleitung aufgefordert, erhalten Sie wahrscheinlich Buildausgabe, die schlägt vor, dass Sie die Assemblys neu zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-121">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="b3c5c-122">Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-122">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="b3c5c-123">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-123">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="b3c5c-124">Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-124">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="b3c5c-125">In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-125">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="b3c5c-126">Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-126">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="b3c5c-127">Das folgende Element hinzufügen, um den ersten konfigurationseigenschaftengruppe (unter der \<PropertyGroup > Tag):</span><span class="sxs-lookup"><span data-stu-id="b3c5c-127">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="b3c5c-128">Das folgende Beispiel zeigt eine beispielhafte Projektdatei mit dem eingefügten Element:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-128">The following shows an example project file with the element inserted:</span></span>

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

3. <span data-ttu-id="b3c5c-129">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-129">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="b3c5c-130">Aktivieren Sie automatische bindungsumleitungen in Web-apps</span><span class="sxs-lookup"><span data-stu-id="b3c5c-130">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="b3c5c-131">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-131">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="b3c5c-132">Da bei Web-Apps die Quellkonfigurationsdatei (web.config) geändert werden muss, werden Bindungsumleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-132">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="b3c5c-133">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-133">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="b3c5c-134">Da Sie immer zum Hinzufügen bindungsumleitungen aufgefordert werden, müssen Sie nicht explizit deaktivieren Sie dieses Feature für eine Web-app.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-134">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="b3c5c-135">So fügen Sie bindungsumleitungen in eine Datei "Web.config" hinzu:</span><span class="sxs-lookup"><span data-stu-id="b3c5c-135">To add binding redirects to a web.config file:</span></span>

1. <span data-ttu-id="b3c5c-136">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-136">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="b3c5c-137">![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="b3c5c-137">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="b3c5c-138">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-138">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="b3c5c-139">Doppelklicken Sie auf die Warnung aus, oder wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-139">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="b3c5c-140">Ein Dialogfeld, in dem Sie die erforderlichen Bindungsumleitungen automatisch zur „web.config“-Quelldatei hinzufügen können, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3c5c-140">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>

   <span data-ttu-id="b3c5c-141">![Dialogfeld "portbindung umleitungs-Berechtigung"](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="b3c5c-141">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="b3c5c-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3c5c-142">See also</span></span>

- [<span data-ttu-id="b3c5c-143">\<BindingRedirect >-Element</span><span class="sxs-lookup"><span data-stu-id="b3c5c-143">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="b3c5c-144">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="b3c5c-144">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
