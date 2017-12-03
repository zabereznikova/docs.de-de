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
ms.openlocfilehash: 325497435e24843cc74e804ef38e562617f27167
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
