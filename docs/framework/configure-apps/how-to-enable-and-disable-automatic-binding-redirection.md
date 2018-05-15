---
title: 'Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung'
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2d71da1b48938f9f98221d86f0f9badee3a17919
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="2d3f6-102">Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="2d3f6-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="2d3f6-103">Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] werden beim Kompilieren von Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, Bindungsumleitungen automatisch zur App-Konfigurationsdatei hinzugefügt, um die Assemblyvereinheitlichung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="2d3f6-104">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="2d3f6-105">Die automatische Bindungsumleitung wirkt sich auf herkömmliche Desktop-Apps und Web-Apps aus, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, obwohl das Verhalten für eine Web-App etwas anders ist.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="2d3f6-106">Sie können die automatische Bindungsumleitung aktivieren, wenn Sie über Apps verfügen, die auf frühere Versionen von .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie manuell erstellte Bindungsumleitungen beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="2d3f6-107">Deaktivieren der automatischen Bindungsumleitungen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="2d3f6-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="2d3f6-108">Automatische Bindungsumleitungen sind bei herkömmlichen Desktop-Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und spätere Versionen abzielen, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="2d3f6-109">Die Bindungsumleitungen werden der Ausgabekonfigurationsdatei (app.config) beim Kompilieren der App hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben, die sonst erfolgen würde.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="2d3f6-110">Die app.config-Quelldatei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-110">The source app.config file is not modified.</span></span> <span data-ttu-id="2d3f6-111">Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für Ihre App ändern.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="2d3f6-112">So deaktivieren Sie automatische Bindungsumleitungen</span><span class="sxs-lookup"><span data-stu-id="2d3f6-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="2d3f6-113">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2d3f6-114">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="2d3f6-115">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="2d3f6-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="2d3f6-116">Ändern Sie `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="2d3f6-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="2d3f6-117">Manuelles Aktivieren von automatischen Bindungsumleitungen</span><span class="sxs-lookup"><span data-stu-id="2d3f6-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="2d3f6-118">Sie können automatische Bindungsumleitungen in vorhandenen Apps aktivieren, die auf frühere Versionen von .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="2d3f6-119">Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden, erhalten Sie wahrscheinlich eine Buildausgabe, die das Zuordnen der Assemblys vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="2d3f6-120">So fügen Sie eine Eigenschaft für manuelle Bindungsumleitungen hinzu</span><span class="sxs-lookup"><span data-stu-id="2d3f6-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="2d3f6-121">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2d3f6-122">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="2d3f6-123">Fügen Sie das folgende Element zur ersten konfigurationseigenschaftengruppe hinzu (unter der \<PropertyGroup >-Tag):</span><span class="sxs-lookup"><span data-stu-id="2d3f6-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="2d3f6-124">Im Folgenden sehen Sie eine beispielhafte Projektdatei mit dem eingefügten Element.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="2d3f6-125">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="2d3f6-126">Aktivieren von automatischen Bindungsumleitungen in Web-Apps</span><span class="sxs-lookup"><span data-stu-id="2d3f6-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="2d3f6-127">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="2d3f6-128">Da bei Web-Apps die Quellkonfigurationsdatei (web.config) geändert werden muss, werden Bindungsumleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="2d3f6-129">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="2d3f6-130">Da Sie immer zum Hinzufügen Bindungsumleitungen aufgefordert werden, müssen Sie diese Funktion bei einer Web-App nicht explizit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="2d3f6-131">So fügen Sie Bindungsumleitungen zu einer web.config-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="2d3f6-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="2d3f6-132">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="2d3f6-133">![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="2d3f6-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="2d3f6-134">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="2d3f6-135">Doppelklicken Sie auf die Warnung.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-135">Double-click the warning.</span></span> <span data-ttu-id="2d3f6-136">(Tastatur: Wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.)</span><span class="sxs-lookup"><span data-stu-id="2d3f6-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="2d3f6-137">Ein Dialogfeld, in dem Sie die erforderlichen Bindungsumleitungen automatisch zur „web.config“-Quelldatei hinzufügen können, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d3f6-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="2d3f6-138">![Dialogfeld für die bindungsumleitung Berechtigung](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="2d3f6-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3f6-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d3f6-139">See Also</span></span>  
 [<span data-ttu-id="2d3f6-140">\<BindingRedirect >-Element</span><span class="sxs-lookup"><span data-stu-id="2d3f6-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="2d3f6-141">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="2d3f6-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
