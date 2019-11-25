---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139661"
---
# <a name="bindings"></a><span data-ttu-id="70b9e-101">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="70b9e-101">\<bindings></span></span>

<span data-ttu-id="70b9e-102">Sie können das `bindings`-Element verwenden, um eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen für Windows Communication Foundation (WCF) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="70b9e-102">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="70b9e-103">Jeder Eintrag ist ein `binding`-Element, das anhand seines eindeutigen `name` identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="70b9e-103">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="70b9e-104">Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="70b9e-104">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="70b9e-105">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="70b9e-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="70b9e-106">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="70b9e-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="70b9e-107">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="70b9e-107">System-provided bindings</span></span>

<span data-ttu-id="70b9e-108">Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel.</span><span class="sxs-lookup"><span data-stu-id="70b9e-108">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="70b9e-109">Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel.</span><span class="sxs-lookup"><span data-stu-id="70b9e-109">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="70b9e-110">Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.</span><span class="sxs-lookup"><span data-stu-id="70b9e-110">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="70b9e-111">Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="70b9e-111">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="70b9e-112">Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="70b9e-112">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="70b9e-113">Es ist nicht möglich, einer vom System bereitgestellten Bindung Elemente oder Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="70b9e-113">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="70b9e-114">Zu diesem Zweck sollten Sie eine benutzerdefinierte Bindung implementieren, wie im Abschnitt [benutzerdefinierte Bindungen](#custom-bindings) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70b9e-114">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="70b9e-115">Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung perfekt imitiert und einige Einstellungen hinzufügt, die von der Benutzeranwendung gesteuert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="70b9e-115">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="70b9e-116">Eine Liste der vom System bereitgestellten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="70b9e-116">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="70b9e-117">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="70b9e-117">Custom bindings</span></span>

<span data-ttu-id="70b9e-118">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="70b9e-118">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="70b9e-119">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="70b9e-119">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="70b9e-120">Jedes Element definiert und konfiguriert ein Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="70b9e-120">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="70b9e-121">Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="70b9e-121">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="70b9e-122">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="70b9e-122">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="70b9e-123">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="70b9e-123">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="70b9e-124">Die erforderliche Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="70b9e-124">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="70b9e-125">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="70b9e-125">Transactions (optional)</span></span>  

2. <span data-ttu-id="70b9e-126">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="70b9e-126">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="70b9e-127">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="70b9e-127">Security (optional)</span></span>  

4. <span data-ttu-id="70b9e-128">Encoder</span><span class="sxs-lookup"><span data-stu-id="70b9e-128">Encoder</span></span>  

5. <span data-ttu-id="70b9e-129">Transport</span><span class="sxs-lookup"><span data-stu-id="70b9e-129">Transport</span></span>  

 <span data-ttu-id="70b9e-130">Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="70b9e-130">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="70b9e-131">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="70b9e-131">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70b9e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70b9e-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="70b9e-133">Bindungen</span><span class="sxs-lookup"><span data-stu-id="70b9e-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="70b9e-134">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="70b9e-134">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="70b9e-135">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="70b9e-135">\<customBinding></span></span>](custombinding.md)
