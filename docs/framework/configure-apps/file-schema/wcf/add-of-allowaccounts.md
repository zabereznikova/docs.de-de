---
title: <add> von <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1ed0b5025ab969c45d7440f2a209426c5c87f549
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920290"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="e6016-102">\<Fügen Sie > \<von allowaccounts hinzu ></span><span class="sxs-lookup"><span data-stu-id="e6016-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="e6016-103">Gibt ein Benutzerkonto für Prozesse an, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6016-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="e6016-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e6016-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6016-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6016-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6016-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6016-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e6016-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6016-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6016-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6016-108">Attributes</span></span>  
  
|<span data-ttu-id="e6016-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6016-109">Attribute</span></span>|<span data-ttu-id="e6016-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6016-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6016-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e6016-111">securityIdentifier</span></span>|<span data-ttu-id="e6016-112">Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6016-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="e6016-113">Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="e6016-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6016-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6016-114">Child Elements</span></span>  
 <span data-ttu-id="e6016-115">Keine</span><span class="sxs-lookup"><span data-stu-id="e6016-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6016-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6016-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e6016-117">Element</span><span class="sxs-lookup"><span data-stu-id="e6016-117">Element</span></span>|<span data-ttu-id="e6016-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6016-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6016-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="e6016-119">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="e6016-120">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6016-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6016-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6016-121">Example</span></span>  
 <span data-ttu-id="e6016-122">Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6016-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6016-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6016-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
