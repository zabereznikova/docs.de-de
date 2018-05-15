---
title: '&lt;Für UserDefinedType&gt;'
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: ffa9480312c278097ae110c686fb507209c117e1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserdefinedtypegt"></a><span data-ttu-id="e9c93-102">&lt;Für UserDefinedType&gt;</span><span class="sxs-lookup"><span data-stu-id="e9c93-102">&lt;userDefinedType&gt;</span></span>
<span data-ttu-id="e9c93-103">Stellt einen benutzerdefinierten Typ (UDT) dar, der in den Dienstvertrag eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9c93-103">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
 <span data-ttu-id="e9c93-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9c93-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9c93-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e9c93-105">\<comContracts></span></span>  
<span data-ttu-id="e9c93-106">\<ComContract ></span><span class="sxs-lookup"><span data-stu-id="e9c93-106">\<comContract></span></span>  
<span data-ttu-id="e9c93-107">\<UserDefinedTypes ></span><span class="sxs-lookup"><span data-stu-id="e9c93-107">\<userDefinedTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c93-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9c93-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9c93-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c93-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9c93-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9c93-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9c93-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9c93-111">Attributes</span></span>  
  
|<span data-ttu-id="e9c93-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e9c93-112">Attribute</span></span>|<span data-ttu-id="e9c93-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9c93-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e9c93-114">Ein optionales Attribut, das eine Zeichenfolge enthält, die den lesbaren Namen des Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="e9c93-114">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="e9c93-115">Dieses wird nicht von der Laufzeit verwendet, sondern hilft einem Reader bei der Typunterscheidung.</span><span class="sxs-lookup"><span data-stu-id="e9c93-115">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="e9c93-116">Eine GUID-Zeichenfolge, mit der der spezifische UDT-Typ in der registrierten Typbibliothek identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e9c93-116">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="e9c93-117">Eine GUID-Zeichenfolge, die die registrierte Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e9c93-117">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="e9c93-118">Eine Zeichenfolge, die die Version der Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e9c93-118">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9c93-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c93-119">Child Elements</span></span>  
 <span data-ttu-id="e9c93-120">Keine</span><span class="sxs-lookup"><span data-stu-id="e9c93-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9c93-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9c93-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e9c93-122">Element</span><span class="sxs-lookup"><span data-stu-id="e9c93-122">Element</span></span>|<span data-ttu-id="e9c93-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9c93-123">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="e9c93-124">Eine Auflistung von `userDefinedType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="e9c93-124">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9c93-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9c93-125">Remarks</span></span>  
 <span data-ttu-id="e9c93-126">Durch Überprüfen der Typbibliothek werden von der Laufzeit der COM+-Integration Dienste erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9c93-126">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="e9c93-127">Wenn COM+-Komponenten Methoden enthalten, die einen VARIANT übergeben, können die tatsächlichen Typen, die vor der Laufzeit übergeben werden sollen, vom System nicht bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="e9c93-127">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="e9c93-128">Aus diesem Grund tritt beim Versuch, einen benutzerdefinierten Typ in einem VARIANT zu übergeben, ein Fehler auf, da der Typ für die Serialisierung nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="e9c93-128">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="e9c93-129">Sie können jedoch der Konfigurationsdatei die UDTs hinzufügen, sodass diese als bekannte Typen im entsprechenden Dienstvertrag eingefügt werden können, um das Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="e9c93-129">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="e9c93-130">Voraussetzung hierfür ist eine eindeutige Identifizierung des UDT und der Verträge, d.&#160;h. der ursprünglich verwendeten COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e9c93-130">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="e9c93-131">Im folgenden Beispiel wird veranschaulicht, wie dem <`userDefinedTypes`>-Abschnitt der Konfigurationsdatei zwei spezifische UDTs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e9c93-131">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <userDefinedTypes>  
         <userDefinedType name="CustomerType"  
            typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"  
            typeLibVersion="1.0"  
            typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">  
         </userDefinedType>  
         <userDefinedType name="AddressType"  
            typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"  
            typeLibVersion="1.0"  
            typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">  
         </userDefinedType>  
      </userDefinedTypes>  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="e9c93-132">Beim Initialisieren des Diensts werden die angegebenen Typen von der Integrationslaufzeit gesucht und der Auflistung der bekannten Typen für die angegebenen Verträge hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e9c93-132">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c93-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c93-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>  
 <xref:System.ServiceModel.Configuration.ComUdtElementCollection>  
 <xref:System.ServiceModel.Configuration.ComUdtElement>  
 [<span data-ttu-id="e9c93-134">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e9c93-134">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="e9c93-135">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e9c93-135">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="e9c93-136">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e9c93-136">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
