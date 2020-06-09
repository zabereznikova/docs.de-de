---
title: Übersicht über die Integration von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c283e7cbc4cb4b8bc37dd1313480410df93a93bf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596824"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="f7da6-102">Übersicht über die Integration von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f7da6-102">Integrating with COM Applications Overview</span></span>

<span data-ttu-id="f7da6-103">Windows Communication Foundation (WCF) stellt dem Entwickler von verwaltetem Code eine umfangreiche Umgebung zum Erstellen verbundener Anwendungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f7da6-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="f7da6-104">Wenn Sie jedoch beträchtliche Investitionen in nicht verwalteten COM-basierten Code haben und nicht migrieren möchten, können Sie WCF-Webdienste mit dem WCF-Dienstmoniker weiterhin direkt in Ihren vorhandenen Code integrieren.</span><span class="sxs-lookup"><span data-stu-id="f7da6-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="f7da6-105">Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7da6-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>

> [!NOTE]
> <span data-ttu-id="f7da6-106">Der Dienstmoniker verwendet einen WCF-Kommunikationskanal für die gesamte Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="f7da6-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="f7da6-107">Die Sicherheits- und Identitätsmechanismen für diesen Channel unterscheiden sich von den Mechanismen in COM- und DCOM-Standardproxys.</span><span class="sxs-lookup"><span data-stu-id="f7da6-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="f7da6-108">Da der Dienstmoniker außerdem einen WCF-Kommunikationskanal verwendet, beträgt der Standard Timeout Zeitraum eine Minute für alle Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="f7da6-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>

<span data-ttu-id="f7da6-109">Der Dienstmoniker wird mit der- `GetObject` Funktion verwendet, um dem nicht verwalteten Entwickler einen stark typisierten, com-spezifischen Ansatz zum Aufrufen von WCF-Webdiensten zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="f7da6-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="f7da6-110">Hierfür ist eine lokale, com-sichtbare Definition des WCF-Webdienst Vertrags und die zu verwendende Bindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7da6-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="f7da6-111">Wie andere WCF-Clients muss der Dienstmoniker einen typisierten Kanal für den Dienst erstellen, obwohl diese Kanal Erstellung für den com-Programmierer beim ersten Methodenaufruf transparent erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f7da6-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>

<span data-ttu-id="f7da6-112">Gemeinsam mit anderen WCF-Clients geben Anwendungen bei der Verwendung des Monikers die Adresse, die Bindung und den Vertrag für die Kommunikation mit einem Dienst an.</span><span class="sxs-lookup"><span data-stu-id="f7da6-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="f7da6-113">Der Vertrag kann mithilfe der folgenden Methoden spezifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="f7da6-113">The contract can be specified in one of the following ways:</span></span>

- <span data-ttu-id="f7da6-114">Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.</span><span class="sxs-lookup"><span data-stu-id="f7da6-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>

- <span data-ttu-id="f7da6-115">WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.</span><span class="sxs-lookup"><span data-stu-id="f7da6-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>

- <span data-ttu-id="f7da6-116">MEX-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX (Metadata Exchange)-Endpunkt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f7da6-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>

## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="f7da6-117">Vom Dienstmoniker unterstützte Parameter</span><span class="sxs-lookup"><span data-stu-id="f7da6-117">Parameters Supported by the Service Moniker</span></span>

<span data-ttu-id="f7da6-118">In der folgenden Tabelle werden die Parameter aufgeführt, die vom Dienstmoniker unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f7da6-118">The following table shows the parameters that are supported by the service moniker.</span></span>

|<span data-ttu-id="f7da6-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7da6-119">Parameter</span></span>|<span data-ttu-id="f7da6-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f7da6-120">Description</span></span>|
|---------------|-----------------|
|`address`|<span data-ttu-id="f7da6-121">URL-Adresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f7da6-121">URL location of the service.</span></span>|
|`binding`|<span data-ttu-id="f7da6-122">Bindungsabschnittsname für die Anwendungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f7da6-122">Binding section name from the application configuration.</span></span>|
|`bindingConfiguration`|<span data-ttu-id="f7da6-123">Benannte Bindungsinstanz innerhalb des benannten Bindungsabschnitts.</span><span class="sxs-lookup"><span data-stu-id="f7da6-123">Named binding instance from within the named binding section.</span></span>|
|`contract`|<span data-ttu-id="f7da6-124">Schnittstellenbezeichner (Interface identifier, IID), der den Dienstvertrag oder den Vertragsnamen (von MEX) darstellt.</span><span class="sxs-lookup"><span data-stu-id="f7da6-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|
|`wsdl`|<span data-ttu-id="f7da6-125">WSDL-Dokument, das eine alternative Form der Vertragsdefinition enthält.</span><span class="sxs-lookup"><span data-stu-id="f7da6-125">WSDL document that provides an alternative form of contract definition.</span></span>|
|`spnIdentity`|<span data-ttu-id="f7da6-126">SPN (Server Principal Name)-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|
|`upnIdentity`|<span data-ttu-id="f7da6-127">UPN (User Principal Name)-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|
|`dnsIdentity`|<span data-ttu-id="f7da6-128">DNS-Identität, die zur Kommunikation mit dem Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-128">DNS identity to be used to communicate with the service.</span></span>|
|`mexAddress`|<span data-ttu-id="f7da6-129">URL-Adresse des MEX-Endpunkts (Metadata Exchange) des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f7da6-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|
|`mexBinding`|<span data-ttu-id="f7da6-130">Bindungsabschnittsname für die Anwendungskonfiguration zur Verbindung mit dem MEX-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f7da6-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|
|`mexBindingConfiguration`|<span data-ttu-id="f7da6-131">Benannte Bindungsinstanz innerhalb des benannten Bindungsabschnitts zur Verbindung mit dem MEX-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f7da6-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|
|`bindingNamespace`|<span data-ttu-id="f7da6-132">Namespace des Bindungsabschnittsnamens für den abgerufenen MEX.</span><span class="sxs-lookup"><span data-stu-id="f7da6-132">Namespace of the binding section name from the retrieved MEX.</span></span>|
|`contractNamespace`|<span data-ttu-id="f7da6-133">Namespace des Vertrags für den abgerufenen MEX.</span><span class="sxs-lookup"><span data-stu-id="f7da6-133">Namespace of the contract from the retrieved MEX.</span></span>|
|`mexSpnIdentity`|<span data-ttu-id="f7da6-134">SPN (Server Principal Name)-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexUpnIdentity`|<span data-ttu-id="f7da6-135">UPN (User Principal Name)-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexDnsIdentity`|<span data-ttu-id="f7da6-136">DNS-Identität, die für die Kommunikation mit dem MEX-Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7da6-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|
|`serializer`|<span data-ttu-id="f7da6-137">Geben Sie entweder die Verwendung des "XML"- oder des "datacontract"-Serialisierungsprogramms an.</span><span class="sxs-lookup"><span data-stu-id="f7da6-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|

> [!NOTE]
> <span data-ttu-id="f7da6-138">Selbst bei Verwendung mit vollständig com-basierten Clients muss der Dienstmoniker WCF und die unterstützende .NET Framework 2,0 auf dem Client Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="f7da6-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="f7da6-139">Außerdem müssen Clientanwendungen, die den Dienstmoniker verwenden, die entsprechende Version der .NET Framework-Laufzeit laden.</span><span class="sxs-lookup"><span data-stu-id="f7da6-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="f7da6-140">Bei Verwendung des Monikers innerhalb von Office-Anwendungen ist möglicherweise eine Konfigurationsdatei erforderlich, um sicherzustellen, dass die richtige Framework-Version geladen ist.</span><span class="sxs-lookup"><span data-stu-id="f7da6-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="f7da6-141">In Excel muss beispielsweise der folgende Text in einer Datei mit dem Namen Excel.exe.config in dasselbe Verzeichnis abgelegt werden wie die Excel.exe-Datei:</span><span class="sxs-lookup"><span data-stu-id="f7da6-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> <span data-ttu-id="f7da6-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="f7da6-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a><span data-ttu-id="f7da6-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7da6-143">See also</span></span>

- [<span data-ttu-id="f7da6-144">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="f7da6-144">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
