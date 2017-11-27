---
title: '&lt;persistableType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c77bdf8ef02edf682ded95ab16b4d56dbf60b4ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="fd897-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="fd897-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="fd897-103">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="fd897-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="fd897-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fd897-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd897-105">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="fd897-105">\<comContracts></span></span>  
<span data-ttu-id="fd897-106">\<ComContract ></span><span class="sxs-lookup"><span data-stu-id="fd897-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd897-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd897-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="fd897-108">Typ</span><span class="sxs-lookup"><span data-stu-id="fd897-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd897-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fd897-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd897-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd897-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd897-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fd897-111">Attributes</span></span>  
  
|<span data-ttu-id="fd897-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="fd897-112">Attribute</span></span>|<span data-ttu-id="fd897-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd897-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd897-114">id</span><span class="sxs-lookup"><span data-stu-id="fd897-114">id</span></span>|<span data-ttu-id="fd897-115">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="fd897-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="fd897-116">Name</span><span class="sxs-lookup"><span data-stu-id="fd897-116">name</span></span>|<span data-ttu-id="fd897-117">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="fd897-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd897-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd897-118">Child Elements</span></span>  
 <span data-ttu-id="fd897-119">Keine</span><span class="sxs-lookup"><span data-stu-id="fd897-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd897-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd897-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fd897-121">Element</span><span class="sxs-lookup"><span data-stu-id="fd897-121">Element</span></span>|<span data-ttu-id="fd897-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd897-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd897-123">\<PersistableTypes ></span><span class="sxs-lookup"><span data-stu-id="fd897-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="fd897-124">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="fd897-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd897-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd897-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="fd897-126">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="fd897-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="fd897-127">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="fd897-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="fd897-128">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="fd897-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
