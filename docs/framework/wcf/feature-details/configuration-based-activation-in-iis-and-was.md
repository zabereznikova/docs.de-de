---
title: Konfigurationsbasierte Aktivierung unter IIS und WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 5e1672f4dd67950178c95d3e043e16072fcd0ef4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593580"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="5d9bb-102">Konfigurationsbasierte Aktivierung unter IIS und WAS</span><span class="sxs-lookup"><span data-stu-id="5d9bb-102">Configuration-Based Activation in IIS and WAS</span></span>

<span data-ttu-id="5d9bb-103">Wenn Sie einen Windows Communication Foundation (WCF)-Dienst unter Internetinformationsdienste (IIS) oder Windows Process Activation Service (was) gehostet haben, müssen Sie normalerweise eine SVC-Datei bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="5d9bb-104">Die SVC-Datei enthält den Namen des Diensts und eine optionale benutzerdefinierte Diensthostfactory.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="5d9bb-105">Diese Zusatzdatei verursacht einen höheren Verwaltungsmehraufwand.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="5d9bb-106">Die konfigurationsbasierte Aktivierungsfunktion entfernt die Anforderung einer SVC-Datei, sodass auch der damit verbundene Mehraufwand entfällt.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>

## <a name="configuration-based-activation"></a><span data-ttu-id="5d9bb-107">Konfigurationsbasierte Aktivierung</span><span class="sxs-lookup"><span data-stu-id="5d9bb-107">Configuration-Based Activation</span></span>

<span data-ttu-id="5d9bb-108">Die konfigurationsbasierte Aktivierung fügt die Metadaten, die zuvor in die SVC-Datei eingefügt wurden, in die Datei "Web.config" ein.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="5d9bb-109">Innerhalb des<`serviceHostingEnvironment`>-Elements ist ein <`serviceActivations`> Element vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="5d9bb-110">Innerhalb des <`serviceActivations`> Element mindestens ein <`add`> Elemente, eines für jeden gehosteten Dienst.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="5d9bb-111">Das <`add`>-Element enthält Attribute, mit denen Sie die relative Adresse für den Dienst und den Diensttyp oder eine Diensthostfactory festlegen können.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="5d9bb-112">Der folgende Konfigurationsbeispielcode zeigt, wie dieser Abschnitt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-112">The following configuration example code shows how this section is used.</span></span>

> [!NOTE]
> <span data-ttu-id="5d9bb-113">Jedes <`add`>-Element muss einen Dienst oder ein Factory-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="5d9bb-114">Es kann auch einen Dienst und Factoryattribute angeben.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-114">Specifying both service and factory attributes is allowed.</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 <span data-ttu-id="5d9bb-115">Wenn dieser Code in der Datei Web.config enthalten ist, können Sie den Dienstquellcode in das Verzeichnis App_Code der Anwendung oder eine kompilierte Assembly im Verzeichnis Bin der Anwendung einfügen.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="5d9bb-116">Bei Verwendung der konfigurationsbasierten Aktivierung wird Inlinecode in SVC-Dateien nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>
> - <span data-ttu-id="5d9bb-117">Das `relativeAddress` Attribut muss auf eine relative Adresse wie " \<sub-directory> /Service.svc" oder "~/ \< Sub-Directory/Service. svc" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>
> - <span data-ttu-id="5d9bb-118">Es wird eine Konfigurationsausnahme ausgelöst, wenn Sie eine relative Adresse registrieren, für die keine bekannte Erweiterung mit WCF-Zuordnung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>
> - <span data-ttu-id="5d9bb-119">Die angegebene relative Adresse ist relativ zum Stamm der virtuellen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-119">The relative address specified is relative to the root of the virtual application.</span></span>
> - <span data-ttu-id="5d9bb-120">Aufgrund des hierarchischen Konfigurationsmodells werden die registrierten relativen Adressen auf Computer- und Siteebene von den virtuellen Anwendungen geerbt.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>
> - <span data-ttu-id="5d9bb-121">Registrierungen in einer Konfigurationsdatei haben Vorrang vor Einstellungen in einer SVC-, XAMLX-, XOML- oder anderen Datei.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>
> - <span data-ttu-id="5d9bb-122">Alle umgekehrten Schrägstriche ('\') in einem URI, der an IIS/WAS gesendet wird, werden automatisch in einen normalen Schrägstrich ('/') konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="5d9bb-123">Wenn eine relative Adresse hinzugefügt wird, die '\' enthält, und Sie einen URI an IIS senden, für den die relative Adresse verwendet wird, wird der umgekehrte Schrägstrich in einen Schrägstrich konvertiert, und IIS kann keine Übereinstimmung mit der relativen Adresse herstellen.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="5d9bb-124">IIS sendet Ablaufverfolgungsinformationen, die angeben, dass keine Übereinstimmungen gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="5d9bb-124">IIS sends out trace information that indicates that there are no matches found.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d9bb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d9bb-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [<span data-ttu-id="5d9bb-126">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="5d9bb-126">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="5d9bb-127">Übersicht über das Hosten von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="5d9bb-127">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md)
- <span data-ttu-id="5d9bb-128">[Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5d9bb-128">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
