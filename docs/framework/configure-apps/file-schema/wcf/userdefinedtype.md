---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: a4bbd677aba27d93389f8d2f99aadd801c86b65f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172839"
---
# \<userDefinedType>

<span data-ttu-id="158e9-101">Stellt einen benutzerdefinierten Typ (UDT) dar, der in den Dienstvertrag eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="158e9-101">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**  
  
## <a name="syntax"></a><span data-ttu-id="158e9-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="158e9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="158e9-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="158e9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="158e9-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="158e9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="158e9-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="158e9-105">Attributes</span></span>  
  
|<span data-ttu-id="158e9-106">attribute</span><span class="sxs-lookup"><span data-stu-id="158e9-106">Attribute</span></span>|<span data-ttu-id="158e9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="158e9-107">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="158e9-108">Ein optionales Attribut, das eine Zeichenfolge enthält, die den lesbaren Namen des Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="158e9-108">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="158e9-109">Dieses wird nicht von der Laufzeit verwendet, sondern hilft einem Reader bei der Typunterscheidung.</span><span class="sxs-lookup"><span data-stu-id="158e9-109">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="158e9-110">Eine GUID-Zeichenfolge, mit der der spezifische UDT-Typ in der registrierten Typbibliothek identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="158e9-110">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="158e9-111">Eine GUID-Zeichenfolge, die die registrierte Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="158e9-111">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="158e9-112">Eine Zeichenfolge, die die Version der Typbibliothek angibt, mit der der Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="158e9-112">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="158e9-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="158e9-113">Child Elements</span></span>  

 <span data-ttu-id="158e9-114">Keine</span><span class="sxs-lookup"><span data-stu-id="158e9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="158e9-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="158e9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="158e9-116">Element</span><span class="sxs-lookup"><span data-stu-id="158e9-116">Element</span></span>|<span data-ttu-id="158e9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="158e9-117">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="158e9-118">Eine Auflistung von `userDefinedType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="158e9-118">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="158e9-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="158e9-119">Remarks</span></span>  

 <span data-ttu-id="158e9-120">Durch Überprüfen der Typbibliothek werden von der Laufzeit der COM+-Integration Dienste erstellt.</span><span class="sxs-lookup"><span data-stu-id="158e9-120">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="158e9-121">Wenn COM+-Komponenten Methoden enthalten, die einen VARIANT übergeben, können die tatsächlichen Typen, die vor der Laufzeit übergeben werden sollen, vom System nicht bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="158e9-121">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="158e9-122">Aus diesem Grund tritt beim Versuch, einen benutzerdefinierten Typ in einem VARIANT zu übergeben, ein Fehler auf, da der Typ für die Serialisierung nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="158e9-122">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="158e9-123">Sie können jedoch der Konfigurationsdatei die UDTs hinzufügen, sodass diese als bekannte Typen im entsprechenden Dienstvertrag eingefügt werden können, um das Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="158e9-123">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="158e9-124">Voraussetzung hierfür ist eine eindeutige Identifizierung des UDT und der Verträge, d.&#160;h. der ursprünglich verwendeten COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="158e9-124">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="158e9-125">Im folgenden Beispiel wird veranschaulicht, wie dem <`userDefinedTypes`>-Abschnitt der Konfigurationsdatei zwei spezifische UDTs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="158e9-125">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
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
  
 <span data-ttu-id="158e9-126">Beim Initialisieren des Diensts werden die angegebenen Typen von der Integrationslaufzeit gesucht und der Auflistung der bekannten Typen für die angegebenen Verträge hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="158e9-126">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="158e9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="158e9-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="158e9-128">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="158e9-128">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="158e9-129">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="158e9-129">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
