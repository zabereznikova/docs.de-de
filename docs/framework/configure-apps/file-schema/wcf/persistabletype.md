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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56443902885e191d93897096e55742f7665ba00a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="d94b7-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="d94b7-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="d94b7-103">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="d94b7-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="d94b7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d94b7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d94b7-105">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="d94b7-105">\<comContracts></span></span>  
<span data-ttu-id="d94b7-106">\<ComContract ></span><span class="sxs-lookup"><span data-stu-id="d94b7-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94b7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d94b7-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="d94b7-108">Typ</span><span class="sxs-lookup"><span data-stu-id="d94b7-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d94b7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d94b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d94b7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d94b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d94b7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d94b7-111">Attributes</span></span>  
  
|<span data-ttu-id="d94b7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d94b7-112">Attribute</span></span>|<span data-ttu-id="d94b7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d94b7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d94b7-114">id</span><span class="sxs-lookup"><span data-stu-id="d94b7-114">id</span></span>|<span data-ttu-id="d94b7-115">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="d94b7-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="d94b7-116">Name</span><span class="sxs-lookup"><span data-stu-id="d94b7-116">name</span></span>|<span data-ttu-id="d94b7-117">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="d94b7-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d94b7-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d94b7-118">Child Elements</span></span>  
 <span data-ttu-id="d94b7-119">Keine</span><span class="sxs-lookup"><span data-stu-id="d94b7-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d94b7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d94b7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d94b7-121">Element</span><span class="sxs-lookup"><span data-stu-id="d94b7-121">Element</span></span>|<span data-ttu-id="d94b7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d94b7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d94b7-123">\<PersistableTypes ></span><span class="sxs-lookup"><span data-stu-id="d94b7-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="d94b7-124">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d94b7-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d94b7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d94b7-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="d94b7-126">\<ComContracts ></span><span class="sxs-lookup"><span data-stu-id="d94b7-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="d94b7-127">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d94b7-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="d94b7-128">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="d94b7-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
