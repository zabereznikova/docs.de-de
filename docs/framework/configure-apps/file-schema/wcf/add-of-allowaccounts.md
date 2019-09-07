---
title: <add> von <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398380"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="707c0-102">\<Fügen Sie > \<von allowaccounts hinzu ></span><span class="sxs-lookup"><span data-stu-id="707c0-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="707c0-103">Gibt ein Benutzerkonto für Prozesse an, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="707c0-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="707c0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="707c0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="707c0-105">&nbsp;&nbsp;[ **\<System. Service Model. Activation->** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="707c0-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="707c0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NET. Pipe->** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="707c0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="707c0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<allowaccounts->** ](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="707c0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="707c0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="707c0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707c0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="707c0-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="707c0-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="707c0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="707c0-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="707c0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="707c0-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="707c0-112">Attributes</span></span>  
  
|<span data-ttu-id="707c0-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="707c0-113">Attribute</span></span>|<span data-ttu-id="707c0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="707c0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="707c0-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="707c0-115">securityIdentifier</span></span>|<span data-ttu-id="707c0-116">Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="707c0-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="707c0-117">Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="707c0-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="707c0-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="707c0-118">Child Elements</span></span>  
 <span data-ttu-id="707c0-119">Keine</span><span class="sxs-lookup"><span data-stu-id="707c0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="707c0-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="707c0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="707c0-121">Element</span><span class="sxs-lookup"><span data-stu-id="707c0-121">Element</span></span>|<span data-ttu-id="707c0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="707c0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="707c0-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="707c0-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="707c0-124">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="707c0-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="707c0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="707c0-125">Example</span></span>  
 <span data-ttu-id="707c0-126">Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="707c0-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="707c0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="707c0-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
