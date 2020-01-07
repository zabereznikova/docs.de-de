---
title: Dienst Beispiele
ms.date: 03/30/2017
ms.assetid: 462a2218-f8c6-4fb7-95bc-64765459c429
ms.openlocfilehash: afc4d20034730421d0b72659be62a64048a4c77e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345124"
---
# <a name="services"></a><span data-ttu-id="edeb2-102">Dienste</span><span class="sxs-lookup"><span data-stu-id="edeb2-102">Services</span></span>

<span data-ttu-id="edeb2-103">Dieser Abschnitt enthält Beispiele, die Windows Communication Foundation (WCF)-Dienste veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="edeb2-103">This section contains samples that demonstrate Windows Communication Foundation (WCF) services.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="edeb2-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="edeb2-104">In this section</span></span>

- <span data-ttu-id="edeb2-105">[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-105">[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)</span></span>\
<span data-ttu-id="edeb2-106">Veranschaulicht das Hosting von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="edeb2-106">Demonstrates hosting WCF services.</span></span>

- <span data-ttu-id="edeb2-107">[Dienst Interoperabilität](service-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-107">[Service Interoperability](service-interoperability.md)</span></span>\
<span data-ttu-id="edeb2-108">Veranschaulicht die Interaktion zwischen WCF und anderen Dienst Technologien.</span><span class="sxs-lookup"><span data-stu-id="edeb2-108">Demonstrates interaction between WCF and other service technologies.</span></span>

- <span data-ttu-id="edeb2-109">[Verhaltens](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-109">[Behaviors](behaviors.md)</span></span>\
<span data-ttu-id="edeb2-110">Veranschaulicht das Verhalten von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="edeb2-110">Demonstrates WCF service behaviors.</span></span>

- <span data-ttu-id="edeb2-111">[Dienst Sicherheits](service-security.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-111">[Service Security](service-security.md)</span></span>\
<span data-ttu-id="edeb2-112">Veranschaulicht die WCF-Dienst Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="edeb2-112">Demonstrates WCF service security.</span></span>

- <span data-ttu-id="edeb2-113">[Vereinfachte Konfiguration für WCF-Dienste](simplified-configuration-for-wcf-services.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-113">[Simplified Configuration for WCF Services](simplified-configuration-for-wcf-services.md)</span></span>\
<span data-ttu-id="edeb2-114">Veranschaulicht, wie ein typischer Dienst und Client mithilfe von WCF implementiert und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="edeb2-114">Demonstrates how to implement and configure a typical service and client using WCF.</span></span>

- <span data-ttu-id="edeb2-115">[Verwendung von Standard Endpunkten](usage-of-standard-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-115">[Usage of Standard Endpoints](usage-of-standard-endpoints.md)</span></span>\
<span data-ttu-id="edeb2-116">Veranschaulicht, wie Standardendpunkte in Dienstkonfigurationsdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="edeb2-116">Demonstrates how to use standard endpoints in service configuration files.</span></span>

- <span data-ttu-id="edeb2-117">[Erweiterte Schutzrichtlinien](extended-protection-policy.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-117">[Extended Protection Policy](extended-protection-policy.md)</span></span>\
<span data-ttu-id="edeb2-118">Veranschaulicht erweiterten Schutz, eine Sicherheitsinitiative zum Schutz vor Man-In-The-Middle-Angriffen (MITM-Angriff, Janusangriff).</span><span class="sxs-lookup"><span data-stu-id="edeb2-118">Demonstrates Extended Protection, a security initiative for protecting against man-in-the-middle (MITM) attacks.</span></span>

- <span data-ttu-id="edeb2-119">\ der [konfigurationskanalfactory](configuration-channel-factory.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-119">[Configuration Channel Factory](configuration-channel-factory.md)\</span></span>
<span data-ttu-id="edeb2-120">Veranschaulicht die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="edeb2-120">Demonstrates the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span>

- <span data-ttu-id="edeb2-121">[Adressierungs](addressing.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-121">[Addressing](addressing.md)</span></span>\
<span data-ttu-id="edeb2-122">Zeigt verschiedene Aspekte und Funktionen von Endpunktadressen.</span><span class="sxs-lookup"><span data-stu-id="edeb2-122">Demonstrates various aspects and features of endpoint addresses.</span></span>

- <span data-ttu-id="edeb2-123">[Imperativer](imperative.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-123">[Imperative](imperative.md)</span></span>\
<span data-ttu-id="edeb2-124">Zeigt, wie eine <xref:System.ServiceModel.WSHttpBinding> für einen Dienstcode definiert wird, anstatt die `wsHttpBinding`-Bindung in der Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="edeb2-124">Demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span>

- <span data-ttu-id="edeb2-125">[Mehrere Verträge](multiple-contracts.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-125">[Multiple Contracts](multiple-contracts.md)</span></span>\
<span data-ttu-id="edeb2-126">Veranschaulicht, wie mehrere Verträge für einen Dienst implementiert werden und wie Endpunkte zur Kommunikation mit den einzelnen implementierten Verträgen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="edeb2-126">Demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span>

- <span data-ttu-id="edeb2-127">[Mehrere Endpunkte](multiple-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-127">[Multiple Endpoints](multiple-endpoints.md)</span></span>\
<span data-ttu-id="edeb2-128">Zeigt, wie mehrere Endpunkte für einen Dienst konfiguriert werden und wie von einem Client mit jedem Endpunkt kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="edeb2-128">Demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span>

- <span data-ttu-id="edeb2-129">[Mehrere Endpunkte an einem einzelnen ListenUri](multiple-endpoints-at-a-single-listenuri.md) -</span><span class="sxs-lookup"><span data-stu-id="edeb2-129">[Multiple Endpoints at a Single ListenUri](multiple-endpoints-at-a-single-listenuri.md)</span></span>\
<span data-ttu-id="edeb2-130">Zeigt einen Dienst, der mehrere Endpunkte unter einem einzelnen `ListenUri` hostet.</span><span class="sxs-lookup"><span data-stu-id="edeb2-130">Demonstrates a service that hosts multiple endpoints at a single `ListenUri`.</span></span>

- <span data-ttu-id="edeb2-131">[OperationContextScope](operationcontextscope.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-131">[OperationContextScope](operationcontextscope.md)</span></span>\
<span data-ttu-id="edeb2-132">Veranschaulicht, wie mithilfe von Headern zusätzliche Informationen über einen WCF-Befehl gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="edeb2-132">Demonstrates how to send extra information on a WCF call using headers.</span></span>

- <span data-ttu-id="edeb2-133">[Dienst Beschreibung](service-description.md)</span><span class="sxs-lookup"><span data-stu-id="edeb2-133">[Service Description](service-description.md)</span></span>\
<span data-ttu-id="edeb2-134">Veranschaulicht, wie ein Dienst seine Dienstbeschreibungsinformationen zur Laufzeit abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="edeb2-134">Demonstrates how a service can retrieve its service description information at runtime.</span></span>

- <span data-ttu-id="edeb2-135">Der [anwirkungs cymode. reentrant](concurrencymode-reentrant.md) -</span><span class="sxs-lookup"><span data-stu-id="edeb2-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)</span></span>\
<span data-ttu-id="edeb2-136">Veranschaulicht, wie der Reentrant-Parallelitätsmodus in einer Dienstimplementierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="edeb2-136">Demonstrates how to use the Reentrant concurrency mode on a service implementation.</span></span>
