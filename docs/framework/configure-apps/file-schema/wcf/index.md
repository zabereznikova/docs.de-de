---
title: WCF-Konfigurationsschema
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 44d5e0acc6f5a9ca43949bce0c7964354ad18270
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573656"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="bb073-102">WCF-Konfigurationsschema</span><span class="sxs-lookup"><span data-stu-id="bb073-102">WCF Configuration Schema</span></span>

<span data-ttu-id="bb073-103">Windows Communication Foundation (WCF)-Konfigurationselemente ermöglichen es Ihnen, WCF-Dienst-und-Client Anwendungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bb073-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="bb073-104">Sie können das [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um Konfigurationsdateien für Clients und Dienste zu erstellen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb073-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="bb073-105">Da die Konfigurationsdateien als XML formatiert sind, müssen Sie mit XML vertraut sein, wenn Sie diese manuell in einem Texteditor bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="bb073-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="bb073-106">Andernfalls treten möglicherweise Probleme auf, wie ein nicht gefundenes XML-Elementtag oder -attribut.</span><span class="sxs-lookup"><span data-stu-id="bb073-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="bb073-107">Das liegt daran, dass bei XML-Elementtags und -attributen zwischen Groß- und Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="bb073-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="bb073-108">Das WCF-Konfigurationssystem basiert auf dem- <xref:System.Configuration> Namespace.</span><span class="sxs-lookup"><span data-stu-id="bb073-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="bb073-109">Deshalb können Sie alle Standardfunktionen verwenden, die vom <xref:System.Configuration>-Namespace bereitgestellt werden, wie die Konfigurationssperre, die Verschlüsselung und das Zusammenführen, um die Sicherheit Ihrer Anwendung und ihrer Konfiguration zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="bb073-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="bb073-110">Weitere Informationen über diese Konzepte finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="bb073-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="bb073-111">[Encrypting Configuration Information (Verschlüsseln von Konfigurationsinformationen)](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb073-111">[Encrypting Configuration Information](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="bb073-112">[Locking Configuration Settings (Sperren von Konfigurationseinstellungen)](/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb073-112">[Locking Configuration Settings](/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="bb073-113">In diesem Abschnitt werden alle möglichen Werte eines Konfigurationselements sowie seine Interaktion mit anderen WCF-Konfigurationselementen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb073-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="bb073-114">Das WCF-Konfigurations Schema wird in der folgenden Abbildung veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bb073-114">The following map illustrates the WCF configuration schema:</span></span>

:::image type="content" source="./media/index/windows-communication-foundation-configuration-schema.gif" alt-text="Diagramm, in dem das WCF-Konfigurations Schema angezeigt wird." lightbox="./media/index/windows-communication-foundation-configuration-schema.gif":::
  
> [!CAUTION]
> <span data-ttu-id="bb073-116">Schützen Sie die WCF-Konfigurations Abschnitte in ihren Anwendungs Konfigurationsdateien (app.config) mit entsprechenden Access Control Listen (ACL), um potenzielle Sicherheitsbedrohungen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="bb073-116">Protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span> <span data-ttu-id="bb073-117">Stellen Sie z. b. sicher, dass nur die entsprechenden Personen auf die Sicherheitseinstellungen für Anwendungs Bindungen oder den Dienstmodell Abschnitt der Konfigurationsdatei für einen Dienst zugreifen bzw. diese ändern können.</span><span class="sxs-lookup"><span data-stu-id="bb073-117">For example, make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb073-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bb073-118">In This Section</span></span>  

 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="bb073-119">Beschreibt das `ServiceModel`-Element.</span><span class="sxs-lookup"><span data-stu-id="bb073-119">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="bb073-120">Konfiguriert das SMSvcHost.exe-Tool.</span><span class="sxs-lookup"><span data-stu-id="bb073-120">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="bb073-121">Das Element der obersten Ebene zum Festlegen von Optionen für die Verwendung von Serialisierern, wie z. B. <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bb073-121">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb073-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="bb073-122">Related Sections</span></span>  

 [<span data-ttu-id="bb073-123">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="bb073-123">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="bb073-124">Beschreibt das Konfigurieren von WCF-Diensten und-Clients.</span><span class="sxs-lookup"><span data-stu-id="bb073-124">Describes how to configure WCF services and clients.</span></span>
