---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083737"
---
# <a name="persistabletype"></a><span data-ttu-id="9a642-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="9a642-101">\<persistableType></span></span>
<span data-ttu-id="9a642-102">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="9a642-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="9a642-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9a642-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9a642-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="9a642-104">\<comContracts></span></span>  
<span data-ttu-id="9a642-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="9a642-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a642-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a642-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="9a642-107">Typ</span><span class="sxs-lookup"><span data-stu-id="9a642-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a642-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9a642-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9a642-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a642-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a642-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a642-110">Attributes</span></span>  
  
|<span data-ttu-id="9a642-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9a642-111">Attribute</span></span>|<span data-ttu-id="9a642-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a642-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a642-113">id</span><span class="sxs-lookup"><span data-stu-id="9a642-113">id</span></span>|<span data-ttu-id="9a642-114">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="9a642-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="9a642-115">Name</span><span class="sxs-lookup"><span data-stu-id="9a642-115">name</span></span>|<span data-ttu-id="9a642-116">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="9a642-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a642-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a642-117">Child Elements</span></span>  
 <span data-ttu-id="9a642-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="9a642-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a642-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9a642-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9a642-120">Element</span><span class="sxs-lookup"><span data-stu-id="9a642-120">Element</span></span>|<span data-ttu-id="9a642-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a642-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a642-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="9a642-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="9a642-123">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="9a642-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a642-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a642-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="9a642-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="9a642-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="9a642-126">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="9a642-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="9a642-127">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="9a642-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
