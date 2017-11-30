---
title: Konfigurieren der Anwendung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f22fac02616070ecd6498ad0e158782001681ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-your-application"></a><span data-ttu-id="44fa4-102">Konfigurieren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="44fa4-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="44fa4-103"> verwendet das .NET-Konfigurationssystem und ermöglicht es Ihnen, computer- und anwendungsspezifische Dienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44fa4-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="44fa4-104">Von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definierte Konfigurationseinstellungen befinden sich in der `<system.serviceModel>`-Abschnittsgruppe.</span><span class="sxs-lookup"><span data-stu-id="44fa4-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="44fa4-105"> zum Konfigurieren eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="44fa4-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="44fa4-106">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="44fa4-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="44fa4-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="44fa4-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="44fa4-108">Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert.</span><span class="sxs-lookup"><span data-stu-id="44fa4-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="44fa4-109">Anwendungseinstellungen in Konfigurationsdateien .NET finden Sie unter [ \<"appSettings" >](http://go.microsoft.com/fwlink/?LinkId=95159).</span><span class="sxs-lookup"><span data-stu-id="44fa4-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="44fa4-110">Verwenden von Configuration Editor</span><span class="sxs-lookup"><span data-stu-id="44fa4-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="44fa4-111">Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) ermöglicht Administratoren und Entwickler erstellen und Ändern von Konfigurationseinstellungen für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienste mit einer grafischen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="44fa4-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="44fa4-112">Mit diesem Tool können Sie die Einstellungen für Bindungen, Verhaltensweisen, Dienste und Diagnosen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwalten, ohne XML-Dateien direkt bearbeiten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="44fa4-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="44fa4-113">Bearbeiten von Konfigurationsdateien in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44fa4-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="44fa4-114">So bearbeiten Sie die Konfigurationsdatei von einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienstprojekt in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], mit der rechten Maustaste in **Projektmappen-Explorer** , und wählen Sie die **WCF-Konfiguration bearbeiten** Kontextmenüelement.</span><span class="sxs-lookup"><span data-stu-id="44fa4-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="44fa4-115">Dadurch wird die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="44fa4-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44fa4-116">Wenn Sie die Konfigurationsdatei des bearbeiten eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Webdienstprojekts in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] mit der rechten Maustaste in **Projektmappen-Explorer**, beachten Sie, dass der **WCF-Konfiguration bearbeiten** Kontextmenüelement fehlt. .</span><span class="sxs-lookup"><span data-stu-id="44fa4-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="44fa4-117">Zur Umgehung dieses Problem, klicken Sie auf die **Tools** Menü, und wählen Sie **WCF-Dienstkonfigurations-Editor**.</span><span class="sxs-lookup"><span data-stu-id="44fa4-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="44fa4-118">Danach können Sie mit der rechten Maustaste einer Konfigurationsdatei und die **WCF-Konfiguration bearbeiten** Kontextmenüelement.</span><span class="sxs-lookup"><span data-stu-id="44fa4-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fa4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44fa4-119">See Also</span></span>  
 [<span data-ttu-id="44fa4-120">Configuration Editor-Tool (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="44fa4-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="44fa4-121">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="44fa4-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="44fa4-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="44fa4-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
