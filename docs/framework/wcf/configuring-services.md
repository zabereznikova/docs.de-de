---
title: Konfigurieren von WCF-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 81727adbf985986a71cc9f9e2d42a1de0cb1fd76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608537"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="b4592-102">Konfigurieren von WCF-Diensten</span><span class="sxs-lookup"><span data-stu-id="b4592-102">Configuring WCF services</span></span>

<span data-ttu-id="b4592-103">Nachdem Sie Ihren Dienstvertrag entworfen und implementiert haben, können Sie den Dienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b4592-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="b4592-104">An diesem Punkt nehmen Sie die Definition und Anpassung vor, wie der Dienst für Clients offengelegt werden soll. Dazu gehört das Angeben der Adresse, unter der der Dienst zugänglich ist, die Transportart und Nachrichtenverschlüsselung, die der Dienst zum Senden und Empfangen von Nachrichten verwendet, sowie der erforderliche Sicherheitstyp.</span><span class="sxs-lookup"><span data-stu-id="b4592-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="b4592-105">Die Konfiguration enthält bei dieser Verwendungsweise alle Möglichkeiten, die Sie zum Definieren und Anpassen der verschiedenen Aspekte eines Diensts verwenden können, ob imperativ im Code oder mithilfe einer Konfigurationsdatei. Dazu gehört auch das Angeben seiner Endpunktadressen, der verwendeten Transportarten und seiner Sicherheitsschemas.</span><span class="sxs-lookup"><span data-stu-id="b4592-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="b4592-106">In der Praxis ist das Schreiben einer Konfiguration einem wesentlichen Teil der WCF-Anwendungen zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="b4592-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4592-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b4592-107">In This Section</span></span>  
 [<span data-ttu-id="b4592-108">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b4592-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="b4592-109">Beginnend mit [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF enthält ein neues Standard-Konfigurationsmodell, das WCF-konfigurationsanforderungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="b4592-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="b4592-110">Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime automatisch Ihren Dienst mit Standardendpunkten, Bindungen und Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="b4592-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="b4592-111">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="b4592-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="b4592-112">Ein Windows Communication Foundation (WCF)-Dienst ist konfigurierbar mit der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Configuration-Technologie.</span><span class="sxs-lookup"><span data-stu-id="b4592-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="b4592-113">In den meisten Fällen werden die XML-Elemente in die Datei "Web.config" für eine Website (Internet Information Services, IIS) hinzugefügt, die einen WCF-Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="b4592-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="b4592-114">Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen Adressen, die für die Kommunikation mit dem Dienst verwendet werden) für einzelne Computer.</span><span class="sxs-lookup"><span data-stu-id="b4592-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="b4592-115">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4592-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="b4592-116">Darüber hinaus werden WCF mehrere vom System bereitgestellte Allgemeine Konfigurationen in Form von Bindungen, mit denen Sie schnell auswählen, die die grundlegenden Features für die Kommunikation Client und Dienst zwischen, z. B. die Transporte, Sicherheit und Codierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4592-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="b4592-117">Endpunkte</span><span class="sxs-lookup"><span data-stu-id="b4592-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="b4592-118">Die gesamte Kommunikation mit einem WCF-Dienst erfolgt über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b4592-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="b4592-119">Endpunkte enthalten den Vertrag, die Konfigurationsinformationen, die in den Bindungen angegeben sind, und die Adressen, die angeben, wo sich der Dienst befindet bzw. wo Informationen zum Dienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4592-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="b4592-120">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="b4592-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="b4592-121">Verwenden von WCF und vorhandene Sicherheitsmechanismen, Sie können die Vertraulichkeit, Integrität, Authentifizierung und Autorisierung in jeden Dienst implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4592-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="b4592-122">Sie können auch eine Überprüfung auf Sicherheitserfolge und -misserfolge durchführen.</span><span class="sxs-lookup"><span data-stu-id="b4592-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="b4592-123">Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten</span><span class="sxs-lookup"><span data-stu-id="b4592-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="b4592-124">Die Anforderungen zum Verwenden eines Dienstes, der über die Interoperabilität mit Diensten und Clients auf beliebigen anderen Plattformen oder Betriebssystemen verfügt, sind in der WS-I Basic Profile 1.1-Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4592-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b4592-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="b4592-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="b4592-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b4592-126">Related Sections</span></span>  
 [<span data-ttu-id="b4592-127">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="b4592-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="b4592-128">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="b4592-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="b4592-129">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="b4592-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="b4592-130">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="b4592-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="b4592-131">Einführung in die Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="b4592-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="b4592-132">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b4592-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4592-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4592-133">See also</span></span>

- [<span data-ttu-id="b4592-134">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="b4592-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="b4592-135">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="b4592-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="b4592-136">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="b4592-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
