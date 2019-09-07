---
title: <secureConversationAuthentication> von <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399947"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="55e9b-102">\<secureconversationauthentication > von \<servicecredential ></span><span class="sxs-lookup"><span data-stu-id="55e9b-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="55e9b-103">Gibt die Einstellungen für einen sicheren Konversationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="55e9b-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="55e9b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55e9b-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="55e9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="55e9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="55e9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="55e9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicecreden->** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="55e9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="55e9b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<secureconversationauthentication->**</span><span class="sxs-lookup"><span data-stu-id="55e9b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e9b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="55e9b-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55e9b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55e9b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="55e9b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55e9b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55e9b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="55e9b-114">Attributes</span></span>  
  
|<span data-ttu-id="55e9b-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="55e9b-115">Attribute</span></span>|<span data-ttu-id="55e9b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55e9b-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="55e9b-117">Eine Zeichenfolge, die den Typ des zu verwendenden <xref:System.ServiceModel.Security.SecurityStateEncoder> angibt.</span><span class="sxs-lookup"><span data-stu-id="55e9b-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55e9b-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e9b-118">Child Elements</span></span>  
 <span data-ttu-id="55e9b-119">Keine</span><span class="sxs-lookup"><span data-stu-id="55e9b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55e9b-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55e9b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="55e9b-121">Element</span><span class="sxs-lookup"><span data-stu-id="55e9b-121">Element</span></span>|<span data-ttu-id="55e9b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55e9b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55e9b-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="55e9b-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="55e9b-124">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="55e9b-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e9b-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55e9b-125">Remarks</span></span>  
 <span data-ttu-id="55e9b-126">Verwenden Sie das Konfigurationselement, um eine Liste bekannter Anspruchstypen für die Serialisierung der SCT-Cookies (Security Context Token) und einen Encoder zum Verschlüsseln und Sichern der Cookieinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55e9b-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="55e9b-127">Weitere Informationen zu SCT finden Sie unter <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="55e9b-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e9b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55e9b-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
