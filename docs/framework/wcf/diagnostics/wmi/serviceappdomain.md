---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
