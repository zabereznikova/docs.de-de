---
title: <add> von <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398380"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="3426f-102">\<add> von \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="3426f-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="3426f-103">Gibt ein Benutzerkonto für Prozesse an, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="3426f-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3426f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3426f-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3426f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3426f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3426f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3426f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3426f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3426f-107">Attributes</span></span>  
  
|<span data-ttu-id="3426f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3426f-108">Attribute</span></span>|<span data-ttu-id="3426f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3426f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3426f-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="3426f-110">securityIdentifier</span></span>|<span data-ttu-id="3426f-111">Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3426f-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="3426f-112">Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="3426f-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3426f-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3426f-113">Child Elements</span></span>  
 <span data-ttu-id="3426f-114">Keine</span><span class="sxs-lookup"><span data-stu-id="3426f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3426f-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3426f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3426f-116">Element</span><span class="sxs-lookup"><span data-stu-id="3426f-116">Element</span></span>|<span data-ttu-id="3426f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3426f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="3426f-118">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="3426f-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3426f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3426f-119">Example</span></span>  
 <span data-ttu-id="3426f-120">Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3426f-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="3426f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3426f-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
