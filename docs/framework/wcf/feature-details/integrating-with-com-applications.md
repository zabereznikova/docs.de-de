---
title: Integrieren von COM-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: bc58e22b64284d66367302d55b5c9554c9ec0d72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268234"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="873ef-102">Integrieren von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="873ef-102">Integrating with COM Applications</span></span>

<span data-ttu-id="873ef-103">Windows Communication Foundation (WCF)-Dienste können mithilfe des WCF-Dienstmonikers direkt in Ihren vorhandenen Code integriert werden.</span><span class="sxs-lookup"><span data-stu-id="873ef-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="873ef-104">Der Dienstmoniker kann in vielen verschiedenen COM-basierten Entwicklungsumgebungen wie Office VBA, Visual Basic 6.0 oder Visual C++ 6.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="873ef-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="873ef-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="873ef-105">In This Section</span></span>  

 [<span data-ttu-id="873ef-106">Übersicht über die Integration von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="873ef-106">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)  
 <span data-ttu-id="873ef-107">Bietet eine Übersicht über die Hauptbestandteile des Integrationsprozesses.</span><span class="sxs-lookup"><span data-stu-id="873ef-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="873ef-108">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="873ef-108">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="873ef-109">Um den WCF-Dienstmoniker in einer COM-Anwendung zu verwenden, registrieren Sie die erforderlichen attributierten Typen bei com, und konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="873ef-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="873ef-110">Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="873ef-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="873ef-111">Erläutert, wie Sie die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments oder aus einem WS-MetadataExchange-Endpunkt abrufen.</span><span class="sxs-lookup"><span data-stu-id="873ef-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="873ef-112">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="873ef-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="873ef-113">Beschreibt, wie ein WCF-Beispiel mit einem WCF-WSDL-Moniker aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="873ef-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="873ef-114">Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen</span><span class="sxs-lookup"><span data-stu-id="873ef-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="873ef-115">Beschreibt, wie ein WCF-Beispiel mit einem WCF-Moniker aufgerufen wird, der einen MEX-Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="873ef-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="873ef-116">Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="873ef-116">How to: Specify Channel Security Credentials</span></span>](how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="873ef-117">Der WCF-Dienstmoniker unterstützt die- `IChannelCredentials` Schnittstelle, die eine Reihe alternativer Methoden zum Angeben von Kanal Anmelde Informationen zulässt.</span><span class="sxs-lookup"><span data-stu-id="873ef-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="873ef-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="873ef-118">Reference</span></span>  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="873ef-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="873ef-119">See also</span></span>

- [<span data-ttu-id="873ef-120">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="873ef-120">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
