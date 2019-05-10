---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 5d6bfb1e4aa1651cd8c3a869f681d71cfb15725c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751871"
---
# <a name="comcontract"></a><span data-ttu-id="e638e-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="e638e-101">\<comContract></span></span>
<span data-ttu-id="e638e-102">Gibt einen Dienstvertrag für die COM+-Integration an.</span><span class="sxs-lookup"><span data-stu-id="e638e-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="e638e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e638e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e638e-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e638e-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e638e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e638e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e638e-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e638e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e638e-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e638e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e638e-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e638e-108">Attributes</span></span>  
  
|<span data-ttu-id="e638e-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="e638e-109">Attribute</span></span>|<span data-ttu-id="e638e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e638e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e638e-111">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="e638e-111">contract</span></span>|<span data-ttu-id="e638e-112">Eine Zeichenfolge, die den Vertragstyp enthält.</span><span class="sxs-lookup"><span data-stu-id="e638e-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="e638e-113">Name</span><span class="sxs-lookup"><span data-stu-id="e638e-113">name</span></span>|<span data-ttu-id="e638e-114">Eine Zeichenfolge, die den Vertragsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="e638e-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="e638e-115">namespace</span><span class="sxs-lookup"><span data-stu-id="e638e-115">namespace</span></span>|<span data-ttu-id="e638e-116">Eine Zeichenfolge, die den Vertragsnamespace enthält.</span><span class="sxs-lookup"><span data-stu-id="e638e-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="e638e-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="e638e-117">requiresSession</span></span>|<span data-ttu-id="e638e-118">Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e638e-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="e638e-119">Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e638e-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="e638e-120">Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="e638e-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="e638e-121">Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="e638e-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e638e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e638e-122">Child Elements</span></span>  
  
|<span data-ttu-id="e638e-123">Element</span><span class="sxs-lookup"><span data-stu-id="e638e-123">Element</span></span>|<span data-ttu-id="e638e-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e638e-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e638e-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="e638e-125">persistableTypes</span></span>|<span data-ttu-id="e638e-126">Alle dauerhaften Typen.</span><span class="sxs-lookup"><span data-stu-id="e638e-126">All the persistable types.</span></span>|  
|<span data-ttu-id="e638e-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="e638e-127">userDefinedTypes</span></span>|<span data-ttu-id="e638e-128">Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e638e-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="e638e-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="e638e-129">exposedMethods</span></span>|<span data-ttu-id="e638e-130">Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e638e-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e638e-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e638e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="e638e-132">Element</span><span class="sxs-lookup"><span data-stu-id="e638e-132">Element</span></span>|<span data-ttu-id="e638e-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e638e-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e638e-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="e638e-134">comContracts</span></span>|<span data-ttu-id="e638e-135">Enthält eine Auflistung von `comContract`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="e638e-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e638e-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e638e-136">Remarks</span></span>  
 <span data-ttu-id="e638e-137">COM+-integrationsdienstverträge sind aktuell auf beschränkt die `http://tempuri.org` -Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e638e-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="e638e-138">Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e638e-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="e638e-139">Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="e638e-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="e638e-140">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="e638e-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e638e-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e638e-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="e638e-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e638e-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="e638e-143">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e638e-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e638e-144">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e638e-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
