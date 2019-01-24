---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 2cab52b09b5cc8455531b5f76b088fd4d835ee3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734895"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="d8272-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="d8272-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="d8272-103">Gibt einen Dienstvertrag für die COM+-Integration an.</span><span class="sxs-lookup"><span data-stu-id="d8272-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="d8272-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d8272-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d8272-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d8272-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8272-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8272-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8272-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8272-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d8272-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8272-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8272-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8272-109">Attributes</span></span>  
  
|<span data-ttu-id="d8272-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d8272-110">Attribute</span></span>|<span data-ttu-id="d8272-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8272-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8272-112">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="d8272-112">contract</span></span>|<span data-ttu-id="d8272-113">Eine Zeichenfolge, die den Vertragstyp enthält.</span><span class="sxs-lookup"><span data-stu-id="d8272-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="d8272-114">Name</span><span class="sxs-lookup"><span data-stu-id="d8272-114">name</span></span>|<span data-ttu-id="d8272-115">Eine Zeichenfolge, die den Vertragsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="d8272-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="d8272-116">namespace</span><span class="sxs-lookup"><span data-stu-id="d8272-116">namespace</span></span>|<span data-ttu-id="d8272-117">Eine Zeichenfolge, die den Vertragsnamespace enthält.</span><span class="sxs-lookup"><span data-stu-id="d8272-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="d8272-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="d8272-118">requiresSession</span></span>|<span data-ttu-id="d8272-119">Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8272-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="d8272-120">Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d8272-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="d8272-121">Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="d8272-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="d8272-122">Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="d8272-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8272-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8272-123">Child Elements</span></span>  
  
|<span data-ttu-id="d8272-124">Element</span><span class="sxs-lookup"><span data-stu-id="d8272-124">Element</span></span>|<span data-ttu-id="d8272-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8272-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8272-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="d8272-126">persistableTypes</span></span>|<span data-ttu-id="d8272-127">Alle dauerhaften Typen.</span><span class="sxs-lookup"><span data-stu-id="d8272-127">All the persistable types.</span></span>|  
|<span data-ttu-id="d8272-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d8272-128">userDefinedTypes</span></span>|<span data-ttu-id="d8272-129">Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8272-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="d8272-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="d8272-130">exposedMethods</span></span>|<span data-ttu-id="d8272-131">Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d8272-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8272-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8272-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d8272-133">Element</span><span class="sxs-lookup"><span data-stu-id="d8272-133">Element</span></span>|<span data-ttu-id="d8272-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8272-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8272-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="d8272-135">comContracts</span></span>|<span data-ttu-id="d8272-136">Enthält eine Auflistung von `comContract`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d8272-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8272-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8272-137">Remarks</span></span>  
 <span data-ttu-id="d8272-138">COM+-integrationsdienstverträge sind aktuell auf beschränkt die `http://tempuri.org` -Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d8272-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="d8272-139">Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8272-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="d8272-140">Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8272-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="d8272-141">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="d8272-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8272-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8272-142">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="d8272-143">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d8272-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="d8272-144">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d8272-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="d8272-145">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="d8272-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
