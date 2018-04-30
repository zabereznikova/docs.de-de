---
title: Windows Communication Foundation-Bindungen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 926cdab8b835aa170fc0cdc0046c3fef579c3fec
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="windows-communcation-foundation-bindings"></a><span data-ttu-id="2745d-102">Windows Communication Foundation-Bindungen</span><span class="sxs-lookup"><span data-stu-id="2745d-102">Windows Communcation Foundation Bindings</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="2745d-103"> unterscheidet, wie die Software für eine Anwendung geschrieben wird und wie die Software mit anderer Software kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="2745d-103"> separates how the software for an application is written from how it communicates with other software.</span></span> <span data-ttu-id="2745d-104">Mit Bindungen werden Transport, Codierung und Protokolldetails angegeben, die für die Kommunikation zwischen Clients und Diensten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2745d-104">Bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2745d-105"> generiert mit Bindungen die zugrunde liegende Übertragungsdarstellung des Endpunkts. Deshalb müssen die an der Kommunikation beteiligten Parteien die Bindungsdetails aufeinander abstimmen.</span><span class="sxs-lookup"><span data-stu-id="2745d-105"> uses bindings to generate the underlying wire representation of the endpoint, so most of the binding details must be agreed upon by the parties that are communicating.</span></span> <span data-ttu-id="2745d-106">Das geschieht am einfachsten, indem die Clients eines Diensts dieselbe Bindung wie der Endpunkt dieses Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="2745d-106">The easiest way to achieve this is for clients of a service to use the same binding that the endpoint for the service uses.</span></span> <span data-ttu-id="2745d-107">Weitere Informationen hierzu finden Sie unter [Bindungen verwenden, und Konfigurieren von Windows Communication Foundation-Dienste und Clients](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).</span><span class="sxs-lookup"><span data-stu-id="2745d-107">For more information about how to do this, see [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).</span></span>  
  
 <span data-ttu-id="2745d-108">Eine Bindung besteht aus einer Auflistung von Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="2745d-108">A binding is made up of a collection of binding elements.</span></span> <span data-ttu-id="2745d-109">Jedes Element beschreibt einige Aspekte der Kommunikation zwischen dem Endpunkt und den Clients.</span><span class="sxs-lookup"><span data-stu-id="2745d-109">Each element describes some aspect of how the endpoint communicates with clients.</span></span> <span data-ttu-id="2745d-110">Eine Bindung muss mindestens ein Transportbindungselement, mindestens ein Nachrichten codierendes Bindungselement (was standardmäßig durch das Transportbindungselement erfolgen kann) und eine beliebige Zahl von sonstigen Protokollbindungselementen umfassen.</span><span class="sxs-lookup"><span data-stu-id="2745d-110">A binding must include at least one transport binding element, at least one message-encoding binding element (which the transport binding element can provide by default), and any number of other protocol binding elements.</span></span> <span data-ttu-id="2745d-111">In dem Prozess, der aus dieser Beschreibung eine Laufzeit aufbaut, kann jedes Bindungselement Code zu dieser Laufzeit beitragen.</span><span class="sxs-lookup"><span data-stu-id="2745d-111">The process that builds a runtime out of this description allows each binding element to contribute code to that runtime.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2745d-112"> stellt Bindungen bereit, die jeweils eine Auswahl häufig verwendeter Bindungselemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="2745d-112"> provides bindings that contain common selections of binding elements.</span></span> <span data-ttu-id="2745d-113">Sie können diese Bindungen mit ihren Standardeinstellungen verwenden oder die Standardwerte den Benutzeranforderungen entsprechend ändern.</span><span class="sxs-lookup"><span data-stu-id="2745d-113">These can be used with their default settings or you can modify those default values according to user requirements.</span></span> <span data-ttu-id="2745d-114">Diese vom System bereitgestellten Bindungen verfügen über Eigenschaften, die eine direkte Steuerung der Bindungselemente und ihrer Einstellungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="2745d-114">These system-provided bindings have properties that allow direct control over the binding elements and their settings.</span></span> <span data-ttu-id="2745d-115">Durch die Vergabe eines eigenen Namens für jede Version der Bindung können Sie leicht mit mehreren Versionen einer Bindung gleichzeitig arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2745d-115">You can also easily work side-by-side with multiple versions of a binding by giving each version of the binding its own name.</span></span> <span data-ttu-id="2745d-116">Weitere Informationen finden Sie unter [Configuring System-Provided Bindungen](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="2745d-116">For details, see [Configuring System-Provided Bindings](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).</span></span>  
  
 <span data-ttu-id="2745d-117">Wenn Sie eine Auflistung mit Bindungselementen benötigen, die in den vom System bereitgestellten Bindungen nicht enthalten ist, können Sie eine benutzerdefinierte Bindung mit einer Auflistung der erforderlichen Bindungselemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="2745d-117">If you need a collection of binding elements not provided by one of these system-provided bindings, you can create a custom binding that consists of the collection of binding elements required.</span></span> <span data-ttu-id="2745d-118">Diese benutzerdefinierten Bindungen sind einfach zu erstellen und erfordern keine neue Klasse, sie verfügen jedoch über keine Eigenschaften zum Steuern der Bindungselemente oder deren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2745d-118">These custom bindings are easy to create and do not require a new class, but they do not provide properties for controlling the binding elements or their settings.</span></span> <span data-ttu-id="2745d-119">Sie können auf die Bindungselemente zugreifen und ihre Einstellungen durch die Auflistung ändern, die sie enthält.</span><span class="sxs-lookup"><span data-stu-id="2745d-119">You can access the binding elements and modify their settings through the collection that contains them.</span></span> <span data-ttu-id="2745d-120">Weitere Informationen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="2745d-120">For details, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2745d-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2745d-121">In This Section</span></span>  
 [<span data-ttu-id="2745d-122">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2745d-122">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 <span data-ttu-id="2745d-123">Beschreibt, wie die Bindungen verwendet und geändert werden, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Unterstützung allgemeiner Szenarien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2745d-123">Describes how to use and modify the bindings that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides to support common scenarios.</span></span>  
  
 [<span data-ttu-id="2745d-124">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2745d-124">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 <span data-ttu-id="2745d-125">Beschreibt, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Bindungen für Dienste und Clients imperativ in Code und deklarativ mithilfe der Konfiguration definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2745d-125">Describes how to define [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bindings for services and clients imperatively in code and declaratively using configuration.</span></span>  
  
 [<span data-ttu-id="2745d-126">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2745d-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 <span data-ttu-id="2745d-127">Beschreibt Zweck und Verwendung einer <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="2745d-127">Describes what a <xref:System.ServiceModel.Channels.CustomBinding> is and when it is used.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2745d-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="2745d-128">Reference</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a><span data-ttu-id="2745d-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2745d-129">Related Sections</span></span>  
 [<span data-ttu-id="2745d-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="2745d-130">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
