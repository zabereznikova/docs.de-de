---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139661"
---
# \<bindings>

<span data-ttu-id="41086-101">Sie können das `bindings` -Element verwenden, um eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen für Windows Communication Foundation (WCF) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="41086-101">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="41086-102">Jeder Eintrag ist ein `binding`-Element, das anhand seines eindeutigen `name` identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="41086-102">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="41086-103">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="41086-103">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="41086-104">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="41086-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="41086-105">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="41086-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="41086-106">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="41086-106">System-provided bindings</span></span>

<span data-ttu-id="41086-107">Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel.</span><span class="sxs-lookup"><span data-stu-id="41086-107">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="41086-108">Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel.</span><span class="sxs-lookup"><span data-stu-id="41086-108">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="41086-109">Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.</span><span class="sxs-lookup"><span data-stu-id="41086-109">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="41086-110">Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="41086-110">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="41086-111">Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="41086-111">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="41086-112">Es ist nicht möglich, einer vom System bereitgestellten Bindung Elemente oder Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="41086-112">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="41086-113">Zu diesem Zweck sollten Sie eine benutzerdefinierte Bindung implementieren, wie im Abschnitt [benutzerdefinierte Bindungen](#custom-bindings) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41086-113">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="41086-114">Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung perfekt imitiert und einige Einstellungen hinzufügt, die von der Benutzeranwendung gesteuert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="41086-114">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="41086-115">Eine Liste der vom System bereitgestellten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="41086-115">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="41086-116">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="41086-116">Custom bindings</span></span>

<span data-ttu-id="41086-117">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="41086-117">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="41086-118">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="41086-118">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="41086-119">Jedes Element definiert und konfiguriert ein Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="41086-119">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="41086-120">Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="41086-120">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="41086-121">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="41086-121">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="41086-122">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="41086-122">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="41086-123">Die erforderliche Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="41086-123">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="41086-124">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="41086-124">Transactions (optional)</span></span>  

2. <span data-ttu-id="41086-125">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="41086-125">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="41086-126">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="41086-126">Security (optional)</span></span>  

4. <span data-ttu-id="41086-127">Encoder</span><span class="sxs-lookup"><span data-stu-id="41086-127">Encoder</span></span>  

5. <span data-ttu-id="41086-128">Transport</span><span class="sxs-lookup"><span data-stu-id="41086-128">Transport</span></span>  

 <span data-ttu-id="41086-129">Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="41086-129">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="41086-130">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="41086-130">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41086-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41086-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="41086-132">Bindungen</span><span class="sxs-lookup"><span data-stu-id="41086-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="41086-133">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="41086-133">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
