---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 35596f32bf0e0de9081bc0d4c33fb370c7ab708b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173782"
---
# \<comContract>

<span data-ttu-id="2da58-101">Gibt einen Dienstvertrag für die COM+-Integration an.</span><span class="sxs-lookup"><span data-stu-id="2da58-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="2da58-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="2da58-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2da58-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2da58-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2da58-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2da58-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2da58-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="2da58-105">Attributes</span></span>  
  
|<span data-ttu-id="2da58-106">attribute</span><span class="sxs-lookup"><span data-stu-id="2da58-106">Attribute</span></span>|<span data-ttu-id="2da58-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2da58-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2da58-108">contract</span><span class="sxs-lookup"><span data-stu-id="2da58-108">contract</span></span>|<span data-ttu-id="2da58-109">Eine Zeichenfolge, die den Vertragstyp enthält.</span><span class="sxs-lookup"><span data-stu-id="2da58-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="2da58-110">name</span><span class="sxs-lookup"><span data-stu-id="2da58-110">name</span></span>|<span data-ttu-id="2da58-111">Eine Zeichenfolge, die den Vertragsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2da58-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="2da58-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="2da58-112">namespace</span></span>|<span data-ttu-id="2da58-113">Eine Zeichenfolge, die den Vertragsnamespace enthält.</span><span class="sxs-lookup"><span data-stu-id="2da58-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="2da58-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="2da58-114">requiresSession</span></span>|<span data-ttu-id="2da58-115">Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2da58-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="2da58-116">Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2da58-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="2da58-117">Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="2da58-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="2da58-118">Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="2da58-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2da58-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2da58-119">Child Elements</span></span>  
  
|<span data-ttu-id="2da58-120">Element</span><span class="sxs-lookup"><span data-stu-id="2da58-120">Element</span></span>|<span data-ttu-id="2da58-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2da58-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2da58-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="2da58-122">persistableTypes</span></span>|<span data-ttu-id="2da58-123">Alle dauerhaften Typen.</span><span class="sxs-lookup"><span data-stu-id="2da58-123">All the persistable types.</span></span>|  
|<span data-ttu-id="2da58-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="2da58-124">userDefinedTypes</span></span>|<span data-ttu-id="2da58-125">Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2da58-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="2da58-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="2da58-126">exposedMethods</span></span>|<span data-ttu-id="2da58-127">Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2da58-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2da58-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2da58-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2da58-129">Element</span><span class="sxs-lookup"><span data-stu-id="2da58-129">Element</span></span>|<span data-ttu-id="2da58-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2da58-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2da58-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="2da58-131">comContracts</span></span>|<span data-ttu-id="2da58-132">Enthält eine Auflistung von `comContract`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="2da58-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2da58-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2da58-133">Remarks</span></span>  

 <span data-ttu-id="2da58-134">Com+-Integrations Dienstverträge sind zurzeit auf den `http://tempuri.org` Namespace beschränkt, und der Vertrags Name wird von der unterstützenden com-Schnittstelle abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2da58-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="2da58-135">Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2da58-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="2da58-136">Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="2da58-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="2da58-137">Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="2da58-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da58-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2da58-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="2da58-139">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2da58-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="2da58-140">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2da58-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
