---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855072"
---
# <a name="persistabletype"></a><span data-ttu-id="ef502-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="ef502-101">\<persistableType></span></span>
<span data-ttu-id="ef502-102">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="ef502-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="ef502-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef502-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef502-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ef502-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ef502-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts->** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="ef502-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="ef502-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract->** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="ef502-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="ef502-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<persistabletypes->** ](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="ef502-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="ef502-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistableType->**</span><span class="sxs-lookup"><span data-stu-id="ef502-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef502-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef502-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="ef502-110">Typ</span><span class="sxs-lookup"><span data-stu-id="ef502-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef502-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef502-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ef502-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef502-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef502-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef502-113">Attributes</span></span>  
  
|<span data-ttu-id="ef502-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ef502-114">Attribute</span></span>|<span data-ttu-id="ef502-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef502-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef502-116">id</span><span class="sxs-lookup"><span data-stu-id="ef502-116">id</span></span>|<span data-ttu-id="ef502-117">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="ef502-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="ef502-118">NAME</span><span class="sxs-lookup"><span data-stu-id="ef502-118">name</span></span>|<span data-ttu-id="ef502-119">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef502-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef502-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef502-120">Child Elements</span></span>  
 <span data-ttu-id="ef502-121">None</span><span class="sxs-lookup"><span data-stu-id="ef502-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef502-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef502-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ef502-123">Element</span><span class="sxs-lookup"><span data-stu-id="ef502-123">Element</span></span>|<span data-ttu-id="ef502-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef502-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef502-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="ef502-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="ef502-126">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="ef502-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef502-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef502-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="ef502-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="ef502-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="ef502-129">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ef502-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ef502-130">Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen</span><span class="sxs-lookup"><span data-stu-id="ef502-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
