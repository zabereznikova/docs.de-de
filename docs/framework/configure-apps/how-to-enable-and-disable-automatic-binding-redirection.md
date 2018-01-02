---
title: 'Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b6887706aeef3855c1e02c8b1379856022cdac04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="2b4f2-102">Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="2b4f2-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="2b4f2-103">Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] werden beim Kompilieren von Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, Bindungsumleitungen automatisch zur App-Konfigurationsdatei hinzugefügt, um die Assemblyvereinheitlichung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="2b4f2-104">Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="2b4f2-105">Die automatische Bindungsumleitung wirkt sich auf herkömmliche Desktop-Apps und Web-Apps aus, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, obwohl das Verhalten für eine Web-App etwas anders ist.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="2b4f2-106">Sie können die automatische Bindungsumleitung aktivieren, wenn Sie über Apps verfügen, die auf frühere Versionen von .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie manuell erstellte Bindungsumleitungen beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="2b4f2-107">Deaktivieren der automatischen Bindungsumleitungen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="2b4f2-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="2b4f2-108">Automatische Bindungsumleitungen sind bei herkömmlichen Desktop-Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und spätere Versionen abzielen, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="2b4f2-109">Die Bindungsumleitungen werden der Ausgabekonfigurationsdatei (app.config) beim Kompilieren der App hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben, die sonst erfolgen würde.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="2b4f2-110">Die app.config-Quelldatei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-110">The source app.config file is not modified.</span></span> <span data-ttu-id="2b4f2-111">Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für Ihre App ändern.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="2b4f2-112">So deaktivieren Sie automatische Bindungsumleitungen</span><span class="sxs-lookup"><span data-stu-id="2b4f2-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="2b4f2-113">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2b4f2-114">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="2b4f2-115">Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:</span><span class="sxs-lookup"><span data-stu-id="2b4f2-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="2b4f2-116">Ändern Sie `true` in `false`:</span><span class="sxs-lookup"><span data-stu-id="2b4f2-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="2b4f2-117">Manuelles Aktivieren von automatischen Bindungsumleitungen</span><span class="sxs-lookup"><span data-stu-id="2b4f2-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="2b4f2-118">Sie können automatische Bindungsumleitungen in vorhandenen Apps aktivieren, die auf frühere Versionen von .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="2b4f2-119">Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden, erhalten Sie wahrscheinlich eine Buildausgabe, die das Zuordnen der Assemblys vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="2b4f2-120">So fügen Sie eine Eigenschaft für manuelle Bindungsumleitungen hinzu</span><span class="sxs-lookup"><span data-stu-id="2b4f2-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="2b4f2-121">Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2b4f2-122">Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="2b4f2-123">Fügen Sie das folgende Element zur ersten konfigurationseigenschaftengruppe hinzu (unter der \<PropertyGroup >-Tag):</span><span class="sxs-lookup"><span data-stu-id="2b4f2-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="2b4f2-124">Im Folgenden sehen Sie eine beispielhafte Projektdatei mit dem eingefügten Element.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="2b4f2-125">Kompilieren Sie Ihre App.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="2b4f2-126">Aktivieren von automatischen Bindungsumleitungen in Web-Apps</span><span class="sxs-lookup"><span data-stu-id="2b4f2-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="2b4f2-127">Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="2b4f2-128">Da bei Web-Apps die Quellkonfigurationsdatei (web.config) geändert werden muss, werden Bindungsumleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="2b4f2-129">Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="2b4f2-130">Da Sie immer zum Hinzufügen Bindungsumleitungen aufgefordert werden, müssen Sie diese Funktion bei einer Web-App nicht explizit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="2b4f2-131">So fügen Sie Bindungsumleitungen zu einer web.config-Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="2b4f2-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="2b4f2-132">Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="2b4f2-133">![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="2b4f2-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="2b4f2-134">Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="2b4f2-135">Doppelklicken Sie auf die Warnung.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-135">Double-click the warning.</span></span> <span data-ttu-id="2b4f2-136">(Tastatur: Wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.)</span><span class="sxs-lookup"><span data-stu-id="2b4f2-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="2b4f2-137">Ein Dialogfeld, in dem Sie die erforderlichen Bindungsumleitungen automatisch zur „web.config“-Quelldatei hinzufügen können, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b4f2-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="2b4f2-138">![Dialogfeld für die bindungsumleitung Berechtigung](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="2b4f2-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4f2-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b4f2-139">See Also</span></span>  
 [<span data-ttu-id="2b4f2-140">\<BindingRedirect >-Element</span><span class="sxs-lookup"><span data-stu-id="2b4f2-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="2b4f2-141">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="2b4f2-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
