---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850028"
---
# <a name="comcontract"></a><span data-ttu-id="15f30-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="15f30-101">\<comContract></span></span>
<span data-ttu-id="15f30-102">Gibt einen Dienstvertrag für die COM+-Integration an.</span><span class="sxs-lookup"><span data-stu-id="15f30-102">Specifies a COM+ integration service contract.</span></span>  
  
<span data-ttu-id="15f30-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15f30-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15f30-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="15f30-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15f30-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts->** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="15f30-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="15f30-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<comContract->**</span><span class="sxs-lookup"><span data-stu-id="15f30-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f30-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="15f30-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15f30-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15f30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15f30-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15f30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15f30-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="15f30-110">Attributes</span></span>  
  
|<span data-ttu-id="15f30-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="15f30-111">Attribute</span></span>|<span data-ttu-id="15f30-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15f30-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15f30-113">Vertrag (Contract)</span><span class="sxs-lookup"><span data-stu-id="15f30-113">contract</span></span>|<span data-ttu-id="15f30-114">Eine Zeichenfolge, die den Vertragstyp enthält.</span><span class="sxs-lookup"><span data-stu-id="15f30-114">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="15f30-115">NAME</span><span class="sxs-lookup"><span data-stu-id="15f30-115">name</span></span>|<span data-ttu-id="15f30-116">Eine Zeichenfolge, die den Vertragsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="15f30-116">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="15f30-117">namespace</span><span class="sxs-lookup"><span data-stu-id="15f30-117">namespace</span></span>|<span data-ttu-id="15f30-118">Eine Zeichenfolge, die den Vertragsnamespace enthält.</span><span class="sxs-lookup"><span data-stu-id="15f30-118">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="15f30-119">requiresSession</span><span class="sxs-lookup"><span data-stu-id="15f30-119">requiresSession</span></span>|<span data-ttu-id="15f30-120">Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="15f30-120">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="15f30-121">Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="15f30-121">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="15f30-122">Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="15f30-122">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="15f30-123">Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="15f30-123">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15f30-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15f30-124">Child Elements</span></span>  
  
|<span data-ttu-id="15f30-125">Element</span><span class="sxs-lookup"><span data-stu-id="15f30-125">Element</span></span>|<span data-ttu-id="15f30-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15f30-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15f30-127">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="15f30-127">persistableTypes</span></span>|<span data-ttu-id="15f30-128">Alle dauerhaften Typen.</span><span class="sxs-lookup"><span data-stu-id="15f30-128">All the persistable types.</span></span>|  
|<span data-ttu-id="15f30-129">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="15f30-129">userDefinedTypes</span></span>|<span data-ttu-id="15f30-130">Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="15f30-130">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="15f30-131">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="15f30-131">exposedMethods</span></span>|<span data-ttu-id="15f30-132">Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="15f30-132">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15f30-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15f30-133">Parent Elements</span></span>  
  
|<span data-ttu-id="15f30-134">Element</span><span class="sxs-lookup"><span data-stu-id="15f30-134">Element</span></span>|<span data-ttu-id="15f30-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15f30-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15f30-136">comContracts</span><span class="sxs-lookup"><span data-stu-id="15f30-136">comContracts</span></span>|<span data-ttu-id="15f30-137">Enthält eine Auflistung von `comContract`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="15f30-137">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15f30-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15f30-138">Remarks</span></span>  
 <span data-ttu-id="15f30-139">Com+-Integrations Dienstverträge sind zurzeit auf `http://tempuri.org` den Namespace beschränkt, und der Vertrags Name wird von der unterstützenden com-Schnittstelle abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="15f30-139">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="15f30-140">Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="15f30-140">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="15f30-141">Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="15f30-141">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="15f30-142">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="15f30-142">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f30-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15f30-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="15f30-144">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="15f30-144">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="15f30-145">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="15f30-145">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="15f30-146">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="15f30-146">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
