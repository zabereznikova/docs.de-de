---
title: '&lt;secureConversationAuthentication&gt; von &lt;serviceCredential&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
author: BrucePerlerMS
ms.openlocfilehash: 3adcf7ba9814bcf494d345cf0e3f47c57df2152c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206462"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="c730f-102">&lt;secureConversationAuthentication&gt; von &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="c730f-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="c730f-103">Gibt die Einstellungen für einen sicheren Konversationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="c730f-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="c730f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c730f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c730f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c730f-105">\<behaviors></span></span>  
<span data-ttu-id="c730f-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c730f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c730f-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c730f-107">\<behavior></span></span>  
<span data-ttu-id="c730f-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c730f-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c730f-109">\<SecureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="c730f-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c730f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c730f-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c730f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c730f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c730f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c730f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c730f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c730f-113">Attributes</span></span>  
  
|<span data-ttu-id="c730f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c730f-114">Attribute</span></span>|<span data-ttu-id="c730f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c730f-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="c730f-116">Eine Zeichenfolge, die den Typ des zu verwendenden <xref:System.ServiceModel.Security.SecurityStateEncoder> angibt.</span><span class="sxs-lookup"><span data-stu-id="c730f-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c730f-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c730f-117">Child Elements</span></span>  
 <span data-ttu-id="c730f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="c730f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c730f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c730f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c730f-120">Element</span><span class="sxs-lookup"><span data-stu-id="c730f-120">Element</span></span>|<span data-ttu-id="c730f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c730f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c730f-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c730f-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="c730f-123">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="c730f-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c730f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c730f-124">Remarks</span></span>  
 <span data-ttu-id="c730f-125">Verwenden Sie das Konfigurationselement, um eine Liste bekannter Anspruchstypen für die Serialisierung der SCT-Cookies (Security Context Token) und einen Encoder zum Verschlüsseln und Sichern der Cookieinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c730f-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="c730f-126">Weitere Informationen zu SCT finden Sie unter <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="c730f-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c730f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c730f-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
