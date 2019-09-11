---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854837"
---
# <a name="userdefinedtype"></a><span data-ttu-id="dfd89-101">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="dfd89-101">\<userDefinedType></span></span>
<span data-ttu-id="dfd89-102">Stellt einen benutzerdefinierten Typ (UDT) dar, der in den Dienstvertrag eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfd89-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
<span data-ttu-id="dfd89-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dfd89-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dfd89-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dfd89-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dfd89-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts->** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="dfd89-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="dfd89-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract->** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="dfd89-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="dfd89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<UserDefinedTypes->** ](userdefinedtypes.md)</span><span class="sxs-lookup"><span data-stu-id="dfd89-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)</span></span>\
<span data-ttu-id="dfd89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<UserDefinedType->**</span><span class="sxs-lookup"><span data-stu-id="dfd89-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfd89-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfd89-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfd89-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dfd89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dfd89-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfd89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfd89-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="dfd89-112">Attributes</span></span>  
  
|<span data-ttu-id="dfd89-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="dfd89-113">Attribute</span></span>|<span data-ttu-id="dfd89-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfd89-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="dfd89-115">Ein optionales Attribut, das eine Zeichenfolge enthält, die den lesbaren Namen des Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="dfd89-115">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="dfd89-116">Dieses wird nicht von der Laufzeit verwendet, sondern hilft einem Reader bei der Typunterscheidung.</span><span class="sxs-lookup"><span data-stu-id="dfd89-116">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="dfd89-117">Eine GUID-Zeichenfolge, mit der der spezifische UDT-Typ in der registrierten Typbibliothek identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="dfd89-117">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="dfd89-118">Eine GUID-Zeichenfolge, die die registrierte Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="dfd89-118">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="dfd89-119">Eine Zeichenfolge, die die Version der Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="dfd89-119">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfd89-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfd89-120">Child Elements</span></span>  
 <span data-ttu-id="dfd89-121">Keine</span><span class="sxs-lookup"><span data-stu-id="dfd89-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfd89-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dfd89-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dfd89-123">Element</span><span class="sxs-lookup"><span data-stu-id="dfd89-123">Element</span></span>|<span data-ttu-id="dfd89-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfd89-124">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="dfd89-125">Eine Auflistung von `userDefinedType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="dfd89-125">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfd89-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfd89-126">Remarks</span></span>  
 <span data-ttu-id="dfd89-127">Durch Überprüfen der Typbibliothek werden von der Laufzeit der COM+-Integration Dienste erstellt.</span><span class="sxs-lookup"><span data-stu-id="dfd89-127">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="dfd89-128">Wenn COM+-Komponenten Methoden enthalten, die einen VARIANT übergeben, können die tatsächlichen Typen, die vor der Laufzeit übergeben werden sollen, vom System nicht bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="dfd89-128">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="dfd89-129">Aus diesem Grund tritt beim Versuch, einen benutzerdefinierten Typ in einem VARIANT zu übergeben, ein Fehler auf, da der Typ für die Serialisierung nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="dfd89-129">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="dfd89-130">Sie können jedoch der Konfigurationsdatei die UDTs hinzufügen, sodass diese als bekannte Typen im entsprechenden Dienstvertrag eingefügt werden können, um das Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="dfd89-130">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="dfd89-131">Voraussetzung hierfür ist eine eindeutige Identifizierung des UDT und der Verträge, d.&#160;h. der ursprünglich verwendeten COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dfd89-131">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="dfd89-132">Im folgenden Beispiel wird das Hinzufügen von zwei spezifischen UDTs`userDefinedTypes`zum < > Abschnitt der Konfigurationsdatei zu diesem Zweck veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dfd89-132">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
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
  
 <span data-ttu-id="dfd89-133">Beim Initialisieren des Diensts werden die angegebenen Typen von der Integrationslaufzeit gesucht und der Auflistung der bekannten Typen für die angegebenen Verträge hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dfd89-133">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd89-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfd89-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="dfd89-135">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="dfd89-135">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="dfd89-136">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="dfd89-136">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="dfd89-137">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="dfd89-137">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
