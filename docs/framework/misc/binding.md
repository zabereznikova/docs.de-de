---
title: '&lt;Bindung&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 874a3766a64a9abb7c35efd5ac0a0f698707281e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindinggt"></a><span data-ttu-id="aaf1c-102">&lt;Bindung&gt;</span><span class="sxs-lookup"><span data-stu-id="aaf1c-102">&lt;binding&gt;</span></span>
<span data-ttu-id="aaf1c-103">Sie können das `binding`-Element zum Konfigurieren verschiedener Typen von vordefinierten Bindungen verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-103">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="aaf1c-104">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="aaf1c-104">System-Provided Binding</span></span>  
 <span data-ttu-id="aaf1c-105">Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-105">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="aaf1c-106">Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-106">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="aaf1c-107">Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-107">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="aaf1c-108">Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-108">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="aaf1c-109">Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-109">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="aaf1c-110">Es ist nicht möglich, Elemente oder Attribute einer vom System bereitgestellten Bindung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-110">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="aaf1c-111">Um dies durchzuführen, müssen Sie eine benutzerdefinierte Bindung definieren, wie im Abschnitt "Benutzerdefinierte Bindung" dieses Themas beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-111">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="aaf1c-112">Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung auf perfekte Weise imitiert und einige Einstellungen hinzufügt, über die die Benutzeranwendung die Kontrolle haben möchte.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-112">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="aaf1c-113">Benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="aaf1c-113">Custom Binding</span></span>  
 <span data-ttu-id="aaf1c-114">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-114">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="aaf1c-115">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-115">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="aaf1c-116">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-116">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="aaf1c-117">Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-117">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="aaf1c-118">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-118">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="aaf1c-119">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-119">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="aaf1c-120">Die empfohlene Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="aaf1c-120">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="aaf1c-121">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="aaf1c-121">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="aaf1c-122">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="aaf1c-122">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="aaf1c-123">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="aaf1c-123">Security (optional)</span></span>  
  
4.  <span data-ttu-id="aaf1c-124">Encoder</span><span class="sxs-lookup"><span data-stu-id="aaf1c-124">Encoder</span></span>  
  
5.  <span data-ttu-id="aaf1c-125">Transport</span><span class="sxs-lookup"><span data-stu-id="aaf1c-125">Transport</span></span>  
  
 <span data-ttu-id="aaf1c-126">Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="aaf1c-126">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf1c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaf1c-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="aaf1c-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="aaf1c-128">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="aaf1c-129">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="aaf1c-129">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="aaf1c-130">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="aaf1c-130">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
