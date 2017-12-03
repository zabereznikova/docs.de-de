---
title: Erweitern von ServiceHost und der Dienstmodellebene
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 67ed4be3211af141af87da2406e81ff5e2fbb767
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="c3da7-102">Erweitern von ServiceHost und der Dienstmodellebene</span><span class="sxs-lookup"><span data-stu-id="c3da7-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="c3da7-103">Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden.</span><span class="sxs-lookup"><span data-stu-id="c3da7-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="c3da7-104">Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, benutzerdefiniertes Verhalten, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c3da7-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3da7-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c3da7-105">In This Section</span></span>  
 [<span data-ttu-id="c3da7-106">Erweitern von Clients</span><span class="sxs-lookup"><span data-stu-id="c3da7-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="c3da7-107">Beschreibt die Schnittstellen, die die Client-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Clientanwendungen einfügen können.</span><span class="sxs-lookup"><span data-stu-id="c3da7-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="c3da7-108">Sie können beispielsweise eine benutzerdefinierte Clientnachrichtenprotokollierung, benutzerdefinierte Nachrichtenserialisierung usw. durchführen.</span><span class="sxs-lookup"><span data-stu-id="c3da7-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="c3da7-109">Erweitern von Verteilern</span><span class="sxs-lookup"><span data-stu-id="c3da7-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="c3da7-110">Beschreibt die Schnittstellen, die die Dienst-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Dienstanwendungen einfügen können.</span><span class="sxs-lookup"><span data-stu-id="c3da7-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="c3da7-111">Sie können beispielsweise eine benutzerdefinierte Dienstprotokollierung, eine Nachrichtenvalidierung aufseiten des Dienstes, einen benutzerdefinierten Versand usw. durchführen.</span><span class="sxs-lookup"><span data-stu-id="c3da7-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="c3da7-112">Erweiterbare Objekte</span><span class="sxs-lookup"><span data-stu-id="c3da7-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="c3da7-113">Beschreibt die fünf erweiterbaren Objekte und das <xref:System.ServiceModel.IExtensibleObject%601>-Muster.</span><span class="sxs-lookup"><span data-stu-id="c3da7-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="c3da7-114">Das erweiterbare Objektmuster wird verwendet, um entweder vorhandene Laufzeitklassen um neue Funktionen zu erweitern oder um einem Objekt neue Zustandsfunktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c3da7-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="c3da7-115">Erweiterungen, die einem der erweiterbaren Objekte zugeordnet sind, ermöglichen es Verhalten in verschiedenen Phasen der Verarbeitung, auf gemeinsam verwendete Zustände und Funktionen zuzugreifen, die an ein zugängliches und allgemeines erweiterbares Objekt angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="c3da7-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="c3da7-116">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="c3da7-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="c3da7-117">Um Einstellungen für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Laufzeit zu ändern bzw. um Erweiterungen einzufügen, verwenden Sie Verhalten.</span><span class="sxs-lookup"><span data-stu-id="c3da7-117">To change settings on or insert extensions in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime, you use Behaviors.</span></span> <span data-ttu-id="c3da7-118">WCF umfasst vom System implementierte Verhalten zum Steuern von Einschränkungen, Instanzen und anderen Dienst- und Vorgangsaspekten.</span><span class="sxs-lookup"><span data-stu-id="c3da7-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="c3da7-119">Dieser Abschnitt beschreibt, wie Sie Ihre eigenen benutzerdefinierten Verhalten erstellen und sie programmatisch bzw. mit Konfigurationsdateien verfügbar machen können.</span><span class="sxs-lookup"><span data-stu-id="c3da7-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="c3da7-120">Erweitern des Hosting mit ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="c3da7-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="c3da7-121">Beschreibt, wie Sie <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> erweitern und die <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>-Klassen verwenden können, um die Hostumgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c3da7-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c3da7-122">Verweis</span><span class="sxs-lookup"><span data-stu-id="c3da7-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c3da7-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c3da7-123">Related Sections</span></span>
