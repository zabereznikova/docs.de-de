---
title: '&lt;Bindungen&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b729141055f67f1d37cadfa4422417fe2d73139e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindingsgt"></a><span data-ttu-id="69500-102">&lt;Bindungen&gt;</span><span class="sxs-lookup"><span data-stu-id="69500-102">&lt;bindings&gt;</span></span>
<span data-ttu-id="69500-103">Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="69500-103">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="69500-104">Jeder Eintrag ist ein `binding`-Element, das anhand seines eindeutigen `name` identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="69500-104">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="69500-105">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="69500-105">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="69500-106">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="69500-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="69500-107">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="69500-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="69500-108">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="69500-108">System-Provided Binding</span></span>  
 <span data-ttu-id="69500-109">Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel.</span><span class="sxs-lookup"><span data-stu-id="69500-109">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="69500-110">Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel.</span><span class="sxs-lookup"><span data-stu-id="69500-110">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="69500-111">Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.</span><span class="sxs-lookup"><span data-stu-id="69500-111">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="69500-112">Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="69500-112">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="69500-113">Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="69500-113">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="69500-114">Es ist nicht möglich, Elemente oder Attribute einer vom System bereitgestellten Bindung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="69500-114">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="69500-115">Um dies durchzuführen, müssen Sie eine benutzerdefinierte Bindung definieren, wie im Abschnitt "Benutzerdefinierte Bindung" dieses Themas beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69500-115">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="69500-116">Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung auf perfekte Weise imitiert und einige Einstellungen hinzufügt, über die die Benutzeranwendung die Kontrolle haben möchte.</span><span class="sxs-lookup"><span data-stu-id="69500-116">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
 <span data-ttu-id="69500-117">Eine Liste der vom System bereitgestellte Bindungen, finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="69500-117">For a list of system-provided bindings, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="69500-118">Benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="69500-118">Custom Binding</span></span>  
 <span data-ttu-id="69500-119">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="69500-119">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="69500-120">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="69500-120">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="69500-121">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="69500-121">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="69500-122">Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="69500-122">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="69500-123">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="69500-123">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="69500-124">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="69500-124">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="69500-125">Die erforderliche Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="69500-125">The required order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="69500-126">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="69500-126">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="69500-127">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="69500-127">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="69500-128">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="69500-128">Security (optional)</span></span>  
  
4.  <span data-ttu-id="69500-129">Encoder</span><span class="sxs-lookup"><span data-stu-id="69500-129">Encoder</span></span>  
  
5.  <span data-ttu-id="69500-130">Transport</span><span class="sxs-lookup"><span data-stu-id="69500-130">Transport</span></span>  
  
 <span data-ttu-id="69500-131">Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="69500-131">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="69500-132">Weitere Informationen zu benutzerdefinierten Bindungen, finden Sie unter [benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="69500-132">For more information on custom bindings, see [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69500-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69500-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="69500-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="69500-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="69500-135">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="69500-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="69500-136">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="69500-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="69500-137">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="69500-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
