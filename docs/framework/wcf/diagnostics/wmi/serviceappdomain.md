---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192238"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Ordnet einer Anwendungsdomäne einen Dienst zu.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
