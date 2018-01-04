---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d948d1c77fc3f188694062ca9dcb3058f408c45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Ordnet einer Anwendungsdomäne einen Dienst zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Mit der ServiceAppDomain-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die ServiceAppDomain-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="ref"></a>ref  
 Datentyp: Dienst  
Qualifizierer: Schlüssel  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Dienst dieser Anwendungsdomäne.  
  
### <a name="ref"></a>ref  
 Datentyp: AppDomainInfo  
Qualifizierer: Schlüssel  
  
 Zugriffstyp: Schreibgeschützt  
  
 Enthält Eigenschaften der Anwendungsdomäne.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
