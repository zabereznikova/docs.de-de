---
title: ServiceToEndpointAssociation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d2755294ba02b4d67bd7f62cf020a44525874d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
