---
title: <secureConversationAuthentication> von <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: be2a9298a78de1503271f41076b9f5bb63c73f74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162237"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="507c5-102">\<secureConversationAuthentication> von \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="507c5-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>

<span data-ttu-id="507c5-103">Gibt die Einstellungen für einen sicheren Konversationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="507c5-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="507c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="507c5-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="507c5-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="507c5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="507c5-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="507c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="507c5-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="507c5-107">Attributes</span></span>  
  
|<span data-ttu-id="507c5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="507c5-108">Attribute</span></span>|<span data-ttu-id="507c5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="507c5-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="507c5-110">Eine Zeichenfolge, die den Typ des zu verwendenden <xref:System.ServiceModel.Security.SecurityStateEncoder> angibt.</span><span class="sxs-lookup"><span data-stu-id="507c5-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="507c5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="507c5-111">Child Elements</span></span>  

 <span data-ttu-id="507c5-112">Keine</span><span class="sxs-lookup"><span data-stu-id="507c5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="507c5-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="507c5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="507c5-114">Element</span><span class="sxs-lookup"><span data-stu-id="507c5-114">Element</span></span>|<span data-ttu-id="507c5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="507c5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="507c5-116">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="507c5-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="507c5-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="507c5-117">Remarks</span></span>  

 <span data-ttu-id="507c5-118">Verwenden Sie das Konfigurationselement, um eine Liste bekannter Anspruchstypen für die Serialisierung der SCT-Cookies (Security Context Token) und einen Encoder zum Verschlüsseln und Sichern der Cookieinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="507c5-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="507c5-119">Weitere Informationen zu SCT finden Sie unter <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="507c5-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507c5-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="507c5-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
