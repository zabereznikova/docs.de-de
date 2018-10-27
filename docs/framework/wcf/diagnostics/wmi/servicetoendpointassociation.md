---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452708"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Ordnet einem Endpunkt einen Dienst zu.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
