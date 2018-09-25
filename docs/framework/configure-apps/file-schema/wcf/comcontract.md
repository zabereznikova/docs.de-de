---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: e2addbada7f55076ae919d93c897991a7ec0fcd8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070304"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="b940b-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="b940b-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="b940b-103">Gibt einen Dienstvertrag für die COM+-Integration an.</span><span class="sxs-lookup"><span data-stu-id="b940b-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="b940b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b940b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b940b-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="b940b-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b940b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b940b-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b940b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b940b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b940b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b940b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b940b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b940b-109">Attributes</span></span>  
  
|<span data-ttu-id="b940b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="b940b-110">Attribute</span></span>|<span data-ttu-id="b940b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b940b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b940b-112">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="b940b-112">contract</span></span>|<span data-ttu-id="b940b-113">Eine Zeichenfolge, die den Vertragstyp enthält.</span><span class="sxs-lookup"><span data-stu-id="b940b-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="b940b-114">Name</span><span class="sxs-lookup"><span data-stu-id="b940b-114">name</span></span>|<span data-ttu-id="b940b-115">Eine Zeichenfolge, die den Vertragsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="b940b-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="b940b-116">namespace</span><span class="sxs-lookup"><span data-stu-id="b940b-116">namespace</span></span>|<span data-ttu-id="b940b-117">Eine Zeichenfolge, die den Vertragsnamespace enthält.</span><span class="sxs-lookup"><span data-stu-id="b940b-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="b940b-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="b940b-118">requiresSession</span></span>|<span data-ttu-id="b940b-119">Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b940b-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="b940b-120">Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b940b-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="b940b-121">Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="b940b-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="b940b-122">Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="b940b-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b940b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b940b-123">Child Elements</span></span>  
  
|<span data-ttu-id="b940b-124">Element</span><span class="sxs-lookup"><span data-stu-id="b940b-124">Element</span></span>|<span data-ttu-id="b940b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b940b-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b940b-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="b940b-126">persistableTypes</span></span>|<span data-ttu-id="b940b-127">Alle dauerhaften Typen.</span><span class="sxs-lookup"><span data-stu-id="b940b-127">All the persistable types.</span></span>|  
|<span data-ttu-id="b940b-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="b940b-128">userDefinedTypes</span></span>|<span data-ttu-id="b940b-129">Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b940b-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="b940b-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="b940b-130">exposedMethods</span></span>|<span data-ttu-id="b940b-131">Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b940b-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b940b-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b940b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b940b-133">Element</span><span class="sxs-lookup"><span data-stu-id="b940b-133">Element</span></span>|<span data-ttu-id="b940b-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b940b-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b940b-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="b940b-135">comContracts</span></span>|<span data-ttu-id="b940b-136">Enthält eine Auflistung von `comContract`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="b940b-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b940b-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b940b-137">Remarks</span></span>  
 <span data-ttu-id="b940b-138">COM+-integrationsdienstverträge sind aktuell auf beschränkt die `http://tempuri.org` -Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b940b-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="b940b-139">Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="b940b-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="b940b-140">Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="b940b-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
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
  
 <span data-ttu-id="b940b-141">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="b940b-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b940b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b940b-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="b940b-143">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="b940b-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="b940b-144">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b940b-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="b940b-145">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b940b-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
