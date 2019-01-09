---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 92c59b3804e22c62340acccc1e12e594203c8e8b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145418"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="8f7ae-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="8f7ae-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="8f7ae-103">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="8f7ae-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="8f7ae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8f7ae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f7ae-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="8f7ae-105">\<comContracts></span></span>  
<span data-ttu-id="8f7ae-106">\<ComContract ></span><span class="sxs-lookup"><span data-stu-id="8f7ae-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7ae-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f7ae-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="8f7ae-108">Typ</span><span class="sxs-lookup"><span data-stu-id="8f7ae-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f7ae-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f7ae-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8f7ae-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f7ae-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f7ae-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f7ae-111">Attributes</span></span>  
  
|<span data-ttu-id="8f7ae-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f7ae-112">Attribute</span></span>|<span data-ttu-id="8f7ae-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f7ae-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f7ae-114">id</span><span class="sxs-lookup"><span data-stu-id="8f7ae-114">id</span></span>|<span data-ttu-id="8f7ae-115">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="8f7ae-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="8f7ae-116">Name</span><span class="sxs-lookup"><span data-stu-id="8f7ae-116">name</span></span>|<span data-ttu-id="8f7ae-117">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="8f7ae-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f7ae-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f7ae-118">Child Elements</span></span>  
 <span data-ttu-id="8f7ae-119">Keine</span><span class="sxs-lookup"><span data-stu-id="8f7ae-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f7ae-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f7ae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8f7ae-121">Element</span><span class="sxs-lookup"><span data-stu-id="8f7ae-121">Element</span></span>|<span data-ttu-id="8f7ae-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f7ae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f7ae-123">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="8f7ae-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="8f7ae-124">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="8f7ae-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f7ae-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f7ae-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="8f7ae-126">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="8f7ae-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="8f7ae-127">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8f7ae-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="8f7ae-128">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="8f7ae-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
