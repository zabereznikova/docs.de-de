---
title: <secureConversationAuthentication> von <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: f35392b91d047c46e65ce433ef544b86cf6c88c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083698"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="24f05-102">\<SecureConversationAuthentication > von \<ServiceCredential ></span><span class="sxs-lookup"><span data-stu-id="24f05-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="24f05-103">Gibt die Einstellungen für einen sicheren Konversationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="24f05-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="24f05-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="24f05-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="24f05-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="24f05-105">\<behaviors></span></span>  
<span data-ttu-id="24f05-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="24f05-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="24f05-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="24f05-107">\<behavior></span></span>  
<span data-ttu-id="24f05-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="24f05-108">\<serviceCredentials></span></span>  
<span data-ttu-id="24f05-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="24f05-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f05-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="24f05-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24f05-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24f05-111">Attributes and Elements</span></span>  
 <span data-ttu-id="24f05-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24f05-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24f05-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="24f05-113">Attributes</span></span>  
  
|<span data-ttu-id="24f05-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="24f05-114">Attribute</span></span>|<span data-ttu-id="24f05-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24f05-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="24f05-116">Eine Zeichenfolge, die den Typ des zu verwendenden <xref:System.ServiceModel.Security.SecurityStateEncoder> angibt.</span><span class="sxs-lookup"><span data-stu-id="24f05-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24f05-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24f05-117">Child Elements</span></span>  
 <span data-ttu-id="24f05-118">Keine</span><span class="sxs-lookup"><span data-stu-id="24f05-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24f05-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24f05-119">Parent Elements</span></span>  
  
|<span data-ttu-id="24f05-120">Element</span><span class="sxs-lookup"><span data-stu-id="24f05-120">Element</span></span>|<span data-ttu-id="24f05-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24f05-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24f05-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="24f05-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="24f05-123">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="24f05-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24f05-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24f05-124">Remarks</span></span>  
 <span data-ttu-id="24f05-125">Verwenden Sie das Konfigurationselement, um eine Liste bekannter Anspruchstypen für die Serialisierung der SCT-Cookies (Security Context Token) und einen Encoder zum Verschlüsseln und Sichern der Cookieinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24f05-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="24f05-126">Weitere Informationen zu SCT finden Sie unter <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="24f05-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f05-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24f05-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
