---
title: <add> von <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: cd4b9fd02eee2de1d0e8be185ffb69c0eae1cd58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181725"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="e0b74-102">\<add> von \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="e0b74-102">\<add> of \<allowAccounts></span></span>

<span data-ttu-id="e0b74-103">Gibt ein Benutzerkonto für Prozesse an, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="e0b74-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e0b74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0b74-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0b74-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b74-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e0b74-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0b74-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0b74-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0b74-107">Attributes</span></span>  
  
|<span data-ttu-id="e0b74-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e0b74-108">Attribute</span></span>|<span data-ttu-id="e0b74-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b74-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0b74-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e0b74-110">securityIdentifier</span></span>|<span data-ttu-id="e0b74-111">Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e0b74-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="e0b74-112">Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="e0b74-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0b74-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b74-113">Child Elements</span></span>  

 <span data-ttu-id="e0b74-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e0b74-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0b74-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b74-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e0b74-116">Element</span><span class="sxs-lookup"><span data-stu-id="e0b74-116">Element</span></span>|<span data-ttu-id="e0b74-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b74-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="e0b74-118">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="e0b74-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0b74-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0b74-119">Example</span></span>  

 <span data-ttu-id="e0b74-120">Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0b74-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0b74-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0b74-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
