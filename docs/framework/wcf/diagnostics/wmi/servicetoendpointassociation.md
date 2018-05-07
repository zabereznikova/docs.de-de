---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Ordnet einem Endpunkt einen Dienst zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die ServiceToEndpointAssociation-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die ServiceToEndpointAssociation-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="ref"></a>ref  
 Datentyp: Dienst  
  
 Zugriffstyp: Schreibgeschützt  
Qualifizierer: Schlüssel  
  
 Der dem Endpunkt zugeordnete Dienst.  
  
### <a name="ref"></a>ref  
 Datentyp: Endpunkt  
  
 Zugriffstyp: Schreibgeschützt  
Qualifizierer: Schlüssel  
  
 Der dem Dienst zugeordnete Endpunkt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
