---
title: Erweitern von WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3d436690108158cfd7675cf00788a564b8a1dc6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="extending-wcf"></a><span data-ttu-id="408e2-102">Erweitern von WCF</span><span class="sxs-lookup"><span data-stu-id="408e2-102">Extending WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="408e2-103"> ermöglicht es Ihnen, Laufzeitkomponenten zu ändern und zu erweitern, um dienstbasierte Anwendungen genau steuern und erweitern zu können.</span><span class="sxs-lookup"><span data-stu-id="408e2-103"> allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="408e2-104">Die Themen in diesem Abschnitt enthalten eingehende Informationen zur Erweiterbarkeitsarchitektur.</span><span class="sxs-lookup"><span data-stu-id="408e2-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="408e2-105">Weitere Informationen zur grundlegenden-Programmierung finden Sie unter [grundlegende WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="408e2-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="408e2-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="408e2-106">In This Section</span></span>  
 [<span data-ttu-id="408e2-107">Erweitern von ServiceHost und der Dienstmodellebene</span><span class="sxs-lookup"><span data-stu-id="408e2-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="408e2-108">Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden.</span><span class="sxs-lookup"><span data-stu-id="408e2-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="408e2-109">Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="408e2-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="408e2-110">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="408e2-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="408e2-111">Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails beschreiben.</span><span class="sxs-lookup"><span data-stu-id="408e2-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="408e2-112">Bindungserweiterungen oder benutzerdefinierte Bindungen implementieren die benutzerdefinierte Kommunikationsfunktionalität, die erforderlich ist, um Anwendungsfunktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="408e2-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="408e2-113">Erweitern der Kanalschicht</span><span class="sxs-lookup"><span data-stu-id="408e2-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="408e2-114">Die Kanalebene liegt unterhalb der Dienstmodellebene und ist für den Austausch von Nachrichten zwischen Clients und Diensten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="408e2-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="408e2-115">Kanalerweiterungen können neue Protokollfunktionalität implementieren, zum Beispiel Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="408e2-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="408e2-116">Kanalerweiterungen transportieren außerdem Funktionalität, zum Beispiel das Implementieren eines neuen Netzwerktransports, um SOAP-Nachrichten zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="408e2-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="408e2-117">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="408e2-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="408e2-118">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] umfasst die Sicherheit die Übertragungssicherheit, (Integrität, Vertraulichkeit und Authentifizierung), die Zugriffssteuerung (Autorisierung) und die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="408e2-118">Security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="408e2-119">Die im `IdentityModel`-Namespace enthaltenen Klassen werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Zugriffssteuerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="408e2-119">The classes found in the `IdentityModel` namespace are used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for access control.</span></span> <span data-ttu-id="408e2-120">Wenn Sie die Sicherheitsarchitektur verinnerlichen, können Sie benutzerdefinierte Anspruchstypen für benutzerdefinierte Zugriffssteuerungssysteme erstellen.</span><span class="sxs-lookup"><span data-stu-id="408e2-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="408e2-121">Erweitern des Metadatensystems</span><span class="sxs-lookup"><span data-stu-id="408e2-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="408e2-122">Beim Metadatensystem von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] handelt es sich um eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die zum Implementieren von dienstbasierten Anwendungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="408e2-122">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="408e2-123">Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.</span><span class="sxs-lookup"><span data-stu-id="408e2-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="408e2-124">Erweitern von Encodern und Serialisierungsprogrammen</span><span class="sxs-lookup"><span data-stu-id="408e2-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="408e2-125">Encoder und Serialisierungsprogramme übersetzen Daten von einem Formular in ein anderes.</span><span class="sxs-lookup"><span data-stu-id="408e2-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="408e2-126">In den Themen in diesem Abschnitt wird erläutert, wie Sie die angegebenen Klassen erweitern, um besondere Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="408e2-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="408e2-127">Verweis</span><span class="sxs-lookup"><span data-stu-id="408e2-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="408e2-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="408e2-128">Related Sections</span></span>  
 [<span data-ttu-id="408e2-129">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="408e2-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="408e2-130">Details zur WCF-Funktion</span><span class="sxs-lookup"><span data-stu-id="408e2-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="408e2-131">Richtlinien und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="408e2-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
