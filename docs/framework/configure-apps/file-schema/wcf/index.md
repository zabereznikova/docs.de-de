---
title: WCF-Konfigurationsschema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7286793d6b2ad94c656dd37cdcc5fe1b0ab85660
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="da54b-102">WCF-Konfigurationsschema</span><span class="sxs-lookup"><span data-stu-id="da54b-102">WCF Configuration Schema</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="da54b-103">-Konfigurationselemente ermöglichen Ihnen, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienst- und -Clientanwendungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="da54b-103"> configuration elements enable you to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service and client applications.</span></span> <span data-ttu-id="da54b-104">Sie können das [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um Konfigurationsdateien für Clients und Dienste zu erstellen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="da54b-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="da54b-105">Da die Konfigurationsdateien als XML formatiert sind, müssen Sie mit XML vertraut sein, wenn Sie diese manuell in einem Texteditor bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="da54b-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="da54b-106">Andernfalls treten möglicherweise Probleme auf, wie ein nicht gefundenes XML-Elementtag oder -attribut.</span><span class="sxs-lookup"><span data-stu-id="da54b-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="da54b-107">Das liegt daran, dass bei XML-Elementtags und -attributen zwischen Groß- und Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="da54b-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="da54b-108">Das [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Konfigurationssystem basiert auf dem <xref:System.Configuration>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="da54b-108">The [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="da54b-109">Deshalb können Sie alle Standardfeatures verwenden, die vom <xref:System.Configuration>-Namespace bereitgestellt werden, wie die Konfigurationssperre, die Verschlüsselung und das Zusammenführen, um die Sicherheit Ihrer Anwendung und ihrer Konfiguration zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="da54b-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="da54b-110">Weitere Informationen über diese Konzepte finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="da54b-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="da54b-111">Encrypting Configuration Information (Verschlüsseln von Konfigurationsinformationen)</span><span class="sxs-lookup"><span data-stu-id="da54b-111">Encrypting Configuration Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="da54b-112">Locking Configuration Settings (Sperren von Konfigurationseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="da54b-112">Locking Configuration Settings</span></span>](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="da54b-113">In diesem Abschnitt werden alle möglichen Werte eines Konfigurationselements sowie seine Interaktion mit anderen WCF-Konfigurationselementen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da54b-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="da54b-114">Die folgende Zuordnung illustriert das WCF-Konfigurationsschema.</span><span class="sxs-lookup"><span data-stu-id="da54b-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="da54b-115">![WCF-Konfigurationsschema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="da54b-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="da54b-116">Sie sollten die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Konfigurationsabschnitte in den Konfigurationsdateien Ihrer Anwendung (app.config) mit den entsprechenden Zugriffssteuerungslisten (ACL) sichern, um mögliche Sicherheitsrisiken zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="da54b-116">You should protect [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="da54b-117">So sollten Sie z.&#160;B. sicherstellen, dass nur die entsprechenden Personen auf die Sicherheitseinstellungen von Anwendungsbindungen oder auf den Dienstmodellabschnitt der Konfigurationsdatei eines Diensts zugreifen oder diese ändern können.</span><span class="sxs-lookup"><span data-stu-id="da54b-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da54b-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da54b-118">In This Section</span></span>  
 [<span data-ttu-id="da54b-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="da54b-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="da54b-120">Beschreibt das `ServiceModel`-Element.</span><span class="sxs-lookup"><span data-stu-id="da54b-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="da54b-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="da54b-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="da54b-122">Konfiguriert das SMSvcHost.exe-Tool.</span><span class="sxs-lookup"><span data-stu-id="da54b-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="da54b-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="da54b-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="da54b-124">Das Element der obersten Ebene zum Festlegen von Optionen für die Verwendung von Serialisierern, wie z. B. <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="da54b-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da54b-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="da54b-125">Related Sections</span></span>  
 [<span data-ttu-id="da54b-126">Konfigurieren von Windows Communication Foundation-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="da54b-126">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 <span data-ttu-id="da54b-127">Beschreibt, wie [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste und -Clients konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="da54b-127">Describes how to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services and clients.</span></span>
