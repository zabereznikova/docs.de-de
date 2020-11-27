---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e08e474be02ee11a6727df8b908b53ab1403f7f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294824"
---
# <a name="configuring-your-application"></a><span data-ttu-id="f8e99-102">Konfigurieren der Anwendung</span><span class="sxs-lookup"><span data-stu-id="f8e99-102">Configuring Your Application</span></span>

<span data-ttu-id="f8e99-103">Windows Communication Foundation (WCF) verwendet das .NET-Konfigurationssystem und ermöglicht es Ihnen, Dienste sowohl im Computer-als auch im Anwendungsbereich zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8e99-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="f8e99-104">Die von WCF definierten Konfigurationseinstellungen befinden sich in der `<system.serviceModel>` Abschnitts Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f8e99-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="f8e99-105">Weitere Informationen zum Konfigurieren eines WCF-Dienstanbieter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f8e99-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="f8e99-106">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="f8e99-106">Configuring Services</span></span>](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="f8e99-107">Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert.</span><span class="sxs-lookup"><span data-stu-id="f8e99-107">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="f8e99-108">Weitere Informationen zu Anwendungseinstellungen in .NET-Konfigurationsdateien finden Sie unter [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="f8e99-108">For more information about application settings in .NET configuration files, see [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="f8e99-109">Verwenden von Configuration Editor</span><span class="sxs-lookup"><span data-stu-id="f8e99-109">Using the Configuration Editor</span></span>  

 <span data-ttu-id="f8e99-110">Mit dem WCF- [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) können Administratoren und Entwickler Konfigurationseinstellungen für WCF-Dienste mithilfe einer grafischen Benutzeroberfläche erstellen und ändern.</span><span class="sxs-lookup"><span data-stu-id="f8e99-110">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="f8e99-111">Mit diesem Tool können Sie Einstellungen für WCF-Bindungen, Verhaltensweisen, Dienste und Diagnosen verwalten, ohne XML-Konfigurationsdateien direkt bearbeiten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f8e99-111">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="f8e99-112">Bearbeiten von Konfigurationsdateien in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f8e99-112">Editing Configuration Files in Visual Studio</span></span>  

 <span data-ttu-id="f8e99-113">Wenn Sie die Konfigurationsdatei eines WCF-Dienst Projekts in Visual Studio bearbeiten möchten, klicken Sie mit der rechten Maustaste auf **Projektmappen-Explorer** , und wählen Sie das Kontextmenü Element **WCF-Konfiguration bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f8e99-113">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="f8e99-114">Dadurch wird das [Tool für den Konfigurations-Editor (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)gestartet.</span><span class="sxs-lookup"><span data-stu-id="f8e99-114">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8e99-115">Wenn Sie die Konfigurationsdatei eines WCF-Webdienst Projekts in Visual Studio bearbeiten, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste darauf klicken, beachten Sie, dass das Kontextmenü Element **WCF-Konfiguration bearbeiten** fehlt.</span><span class="sxs-lookup"><span data-stu-id="f8e99-115">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="f8e99-116">Um dieses Problem zu umgehen, klicken Sie auf **das Menü Extras** , und wählen Sie **WCF-Dienst Konfigurations-Editor** aus.</span><span class="sxs-lookup"><span data-stu-id="f8e99-116">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="f8e99-117">Anschließend können Sie mit der rechten Maustaste auf eine Konfigurationsdatei klicken und das Kontextmenü Element **WCF-Konfiguration bearbeiten** verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8e99-117">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e99-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8e99-118">See also</span></span>

- [<span data-ttu-id="f8e99-119">Configuration Editor-Tool (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="f8e99-119">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="f8e99-120">Konfigurieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="f8e99-120">Configuring Services</span></span>](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
