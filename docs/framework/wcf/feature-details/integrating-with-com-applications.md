---
title: Integrieren von COM-Anwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 130a7cda170721f34a5b44f3361bd591d6375267
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="89442-102">Integrieren von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="89442-102">Integrating with COM Applications</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="89442-103">-Dienste können mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker direkt in den vorhandenen Code integriert werden.</span><span class="sxs-lookup"><span data-stu-id="89442-103"> services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="89442-104">Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89442-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89442-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="89442-105">In This Section</span></span>  
 [<span data-ttu-id="89442-106">Übersicht über die Integration von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="89442-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="89442-107">Bietet eine Übersicht über die Hauptbestandteile des Integrationsprozesses.</span><span class="sxs-lookup"><span data-stu-id="89442-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="89442-108">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="89442-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="89442-109">Zur Verwendung des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmonikers in einer COM-Anwendung müssen die erforderlichen attributierten Typen bei COM registriert werden. Des Weiteren müssen die COM-Anwendung sowie der Moniker mit der erforderlichen Bindungskonfiguration konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="89442-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="89442-110">Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="89442-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="89442-111">Erläutert, wie Sie die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments oder aus einem WS-MetadataExchange-Endpunkt abrufen.</span><span class="sxs-lookup"><span data-stu-id="89442-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="89442-112">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="89442-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="89442-113">Beschreibt das Aufrufen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiels mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-WSDL-Moniker.</span><span class="sxs-lookup"><span data-stu-id="89442-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="89442-114">Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen</span><span class="sxs-lookup"><span data-stu-id="89442-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="89442-115">Beschreibt das Aufrufen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beispiels mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Moniker, der einen MEX-Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="89442-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="89442-116">Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="89442-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="89442-117">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker unterstützt die `IChannelCredentials`-Schnittstelle, die andere Methoden zur Angabe von Kanalanmeldeinformationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="89442-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="89442-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="89442-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="89442-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89442-119">See Also</span></span>  
 [<span data-ttu-id="89442-120">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="89442-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
