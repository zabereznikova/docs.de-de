---
title: '&lt;add&gt; von &lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 964e1ebc3dfc39a06b82dd1b6438e34642635393
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="58fa0-102">&lt;add&gt; von &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="58fa0-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="58fa0-103">Gibt ein Benutzerkonto für Prozesse an, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="58fa0-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="58fa0-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="58fa0-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58fa0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58fa0-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58fa0-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58fa0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="58fa0-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58fa0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58fa0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="58fa0-108">Attributes</span></span>  
  
|<span data-ttu-id="58fa0-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="58fa0-109">Attribute</span></span>|<span data-ttu-id="58fa0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58fa0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58fa0-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="58fa0-111">securityIdentifier</span></span>|<span data-ttu-id="58fa0-112">Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="58fa0-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="58fa0-113">Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="58fa0-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58fa0-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58fa0-114">Child Elements</span></span>  
 <span data-ttu-id="58fa0-115">Keine</span><span class="sxs-lookup"><span data-stu-id="58fa0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58fa0-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58fa0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="58fa0-117">Element</span><span class="sxs-lookup"><span data-stu-id="58fa0-117">Element</span></span>|<span data-ttu-id="58fa0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58fa0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58fa0-119">\<AllowAccounts ></span><span class="sxs-lookup"><span data-stu-id="58fa0-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="58fa0-120">Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier`-Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="58fa0-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58fa0-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58fa0-121">Example</span></span>  
 <span data-ttu-id="58fa0-122">Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="58fa0-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58fa0-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58fa0-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
