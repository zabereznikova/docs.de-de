---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 86a6f975b05133d5f9f21fcfb82ef4c23d2ffaba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148811"
---
# \<useManagedPresentation>

<span data-ttu-id="ee861-101">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee861-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ee861-102">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ee861-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="ee861-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee861-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee861-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ee861-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ee861-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ee861-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee861-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="ee861-106">Attributes</span></span>  

 <span data-ttu-id="ee861-107">Keine</span><span class="sxs-lookup"><span data-stu-id="ee861-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ee861-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee861-108">Child Elements</span></span>  

 <span data-ttu-id="ee861-109">Keine</span><span class="sxs-lookup"><span data-stu-id="ee861-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee861-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee861-110">Parent Elements</span></span>  
  
|<span data-ttu-id="ee861-111">Element</span><span class="sxs-lookup"><span data-stu-id="ee861-111">Element</span></span>|<span data-ttu-id="ee861-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee861-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ee861-113">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ee861-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee861-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ee861-114">Remarks</span></span>  

 <span data-ttu-id="ee861-115">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee861-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="ee861-116">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="ee861-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee861-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee861-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ee861-118">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ee861-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ee861-119">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ee861-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ee861-120">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ee861-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
