---
title: <binding>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb51eb1962603439b89a203eb668dfb543049170
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271472"
---
# <a name="binding"></a><span data-ttu-id="68792-101">\<binding></span><span class="sxs-lookup"><span data-stu-id="68792-101">\<binding></span></span>
<span data-ttu-id="68792-102">Sie können das `binding`-Element zum Konfigurieren verschiedener Typen von vordefinierten Bindungen verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="68792-102">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="68792-103">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="68792-103">System-Provided Binding</span></span>  
 <span data-ttu-id="68792-104">Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel.</span><span class="sxs-lookup"><span data-stu-id="68792-104">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="68792-105">Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel.</span><span class="sxs-lookup"><span data-stu-id="68792-105">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="68792-106">Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.</span><span class="sxs-lookup"><span data-stu-id="68792-106">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="68792-107">Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="68792-107">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="68792-108">Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="68792-108">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="68792-109">Es ist nicht möglich, Elemente oder Attribute einer vom System bereitgestellten Bindung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="68792-109">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="68792-110">Um dies durchzuführen, müssen Sie eine benutzerdefinierte Bindung definieren, wie im Abschnitt "Benutzerdefinierte Bindung" dieses Themas beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68792-110">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="68792-111">Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung auf perfekte Weise imitiert und einige Einstellungen hinzufügt, über die die Benutzeranwendung die Kontrolle haben möchte.</span><span class="sxs-lookup"><span data-stu-id="68792-111">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="68792-112">Benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="68792-112">Custom Binding</span></span>  
 <span data-ttu-id="68792-113">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="68792-113">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="68792-114">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="68792-114">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="68792-115">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="68792-115">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="68792-116">Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="68792-116">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="68792-117">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="68792-117">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="68792-118">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="68792-118">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="68792-119">Die empfohlene Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="68792-119">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="68792-120">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="68792-120">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="68792-121">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="68792-121">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="68792-122">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="68792-122">Security (optional)</span></span>  
  
4.  <span data-ttu-id="68792-123">Encoder</span><span class="sxs-lookup"><span data-stu-id="68792-123">Encoder</span></span>  
  
5.  <span data-ttu-id="68792-124">Transport</span><span class="sxs-lookup"><span data-stu-id="68792-124">Transport</span></span>  
  
 <span data-ttu-id="68792-125">Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="68792-125">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68792-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68792-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [<span data-ttu-id="68792-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="68792-127">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="68792-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="68792-128">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="68792-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="68792-129">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
