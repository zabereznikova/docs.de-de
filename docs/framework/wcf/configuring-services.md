---
title: Konfigurieren von WCF-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 332a88530010197187ca3ea787e152b0c95a5514
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141587"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="9848a-102">Konfigurieren von WCF-Diensten</span><span class="sxs-lookup"><span data-stu-id="9848a-102">Configuring WCF services</span></span>

<span data-ttu-id="9848a-103">Nachdem Sie Ihren Dienstvertrag entworfen und implementiert haben, können Sie den Dienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9848a-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="9848a-104">An diesem Punkt nehmen Sie die Definition und Anpassung vor, wie der Dienst für Clients offengelegt werden soll. Dazu gehört das Angeben der Adresse, unter der der Dienst zugänglich ist, die Transportart und Nachrichtenverschlüsselung, die der Dienst zum Senden und Empfangen von Nachrichten verwendet, sowie der erforderliche Sicherheitstyp.</span><span class="sxs-lookup"><span data-stu-id="9848a-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="9848a-105">Die Konfiguration enthält bei dieser Verwendungsweise alle Möglichkeiten, die Sie zum Definieren und Anpassen der verschiedenen Aspekte eines Diensts verwenden können, ob imperativ im Code oder mithilfe einer Konfigurationsdatei. Dazu gehört auch das Angeben seiner Endpunktadressen, der verwendeten Transportarten und seiner Sicherheitsschemas.</span><span class="sxs-lookup"><span data-stu-id="9848a-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="9848a-106">In der Praxis ist das Schreiben von Konfigurationen ein wesentlicher Bestandteil der Programmierung von WCF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9848a-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9848a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9848a-107">In This Section</span></span>  
 [<span data-ttu-id="9848a-108">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9848a-108">Simplified Configuration</span></span>](simplified-configuration.md)  
 <span data-ttu-id="9848a-109">Ab .NET Framework 4 enthält WCF ein neues Standard Konfigurations Modell, das die WCF-Konfigurations Anforderungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="9848a-109">Starting with .NET Framework 4, WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="9848a-110">Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit Standard Endpunkten, Bindungen und Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="9848a-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="9848a-111">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="9848a-111">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
 <span data-ttu-id="9848a-112">Ein Windows Communication Foundation (WCF)-Dienst kann mit der .NET Framework-Konfigurations Technologie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9848a-112">A Windows Communication Foundation (WCF) service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="9848a-113">In den meisten Fällen werden XML-Elemente der Datei "Web. config" für eine Internetinformationsdienste (IIS)-Website hinzugefügt, die einen WCF-Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="9848a-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="9848a-114">Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen Adressen, die für die Kommunikation mit dem Dienst verwendet werden) für einzelne Computer.</span><span class="sxs-lookup"><span data-stu-id="9848a-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="9848a-115">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9848a-115">Bindings</span></span>](bindings.md)  
 <span data-ttu-id="9848a-116">Außerdem umfasst WCF mehrere vom System bereitgestellte allgemeine Konfigurationen in Form von Bindungen, mit denen Sie schnell die grundlegendsten Features für die Kommunikation zwischen Client und Dienst auswählen können, wie z. b. die verwendeten Transporte, Sicherheit und Nachrichten Codierungen.</span><span class="sxs-lookup"><span data-stu-id="9848a-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="9848a-117">Endpunkte</span><span class="sxs-lookup"><span data-stu-id="9848a-117">Endpoints</span></span>](endpoints.md)  
 <span data-ttu-id="9848a-118">Die gesamte Kommunikation mit einem WCF-Dienst erfolgt über die *Endpunkte* des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="9848a-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="9848a-119">Endpunkte enthalten den Vertrag, die Konfigurationsinformationen, die in den Bindungen angegeben sind, und die Adressen, die angeben, wo sich der Dienst befindet bzw. wo Informationen zum Dienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9848a-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="9848a-120">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="9848a-120">Securing Services</span></span>](securing-services.md)  
 <span data-ttu-id="9848a-121">Mithilfe von WCF und vorhandenen Sicherheitsmechanismen können Sie Vertraulichkeit, Integrität, Authentifizierung und Autorisierung in beliebige Dienste implementieren.</span><span class="sxs-lookup"><span data-stu-id="9848a-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="9848a-122">Sie können auch eine Überprüfung auf Sicherheitserfolge und -misserfolge durchführen.</span><span class="sxs-lookup"><span data-stu-id="9848a-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="9848a-123">Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten</span><span class="sxs-lookup"><span data-stu-id="9848a-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="9848a-124">Die Anforderungen zum Verwenden eines Dienstes, der über die Interoperabilität mit Diensten und Clients auf beliebigen anderen Plattformen oder Betriebssystemen verfügt, sind in der WS-I Basic Profile 1.1-Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9848a-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9848a-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="9848a-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="9848a-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9848a-126">Related Sections</span></span>  
 [<span data-ttu-id="9848a-127">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="9848a-127">Basic Programming Lifecycle</span></span>](basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="9848a-128">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="9848a-128">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)  
  
 [<span data-ttu-id="9848a-129">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="9848a-129">Hosting Services</span></span>](hosting-services.md)  
  
 [<span data-ttu-id="9848a-130">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="9848a-130">Building Clients</span></span>](building-clients.md)  
  
 [<span data-ttu-id="9848a-131">Einführung in die Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="9848a-131">Introduction to Extensibility</span></span>](introduction-to-extensibility.md)  
  
 [<span data-ttu-id="9848a-132">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="9848a-132">Administration and Diagnostics</span></span>](./diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="9848a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9848a-133">See also</span></span>

- [<span data-ttu-id="9848a-134">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="9848a-134">Basic WCF Programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="9848a-135">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="9848a-135">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="9848a-136">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="9848a-136">WCF Feature Details</span></span>](./feature-details/index.md)
