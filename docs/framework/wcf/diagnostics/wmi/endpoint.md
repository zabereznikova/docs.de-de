---
title: Endpunkt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef4e27f6e7a45fe705aa09827702a64c960b6a16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint"></a>Endpunkt
Endpunkt  
  
## <a name="syntax"></a>Syntax  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der Endpoint-Klasse wird die folgende Methode definiert:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Ruft den Instanznamen des Vorgangsleistungsindikators ab.|  
  
## <a name="properties"></a>Eigenschaften  
 Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="address"></a>Adresse  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der die Adresse des Endpunkts enthält.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Identität des Endpunkts.  
  
### <a name="appdomainid"></a>AppDomainId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anwendungsdomänen-ID der Anwendungsdomäne, von der der Endpunkt gehostet wird.  
  
### <a name="behaviors"></a>Verhalten  
 Datentyp: Behavior-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung der von diesem Endpunkt implementierten Verhaltensweisen.  
  
### <a name="binding"></a>Bindung  
 Datentyp: Bindung  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die von diesem Endpunkt verwendete Bindung.  
  
### <a name="contractname"></a>ContractName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Instanzname der Leistungsindikatoren des Endpunkts.  
  
### <a name="listenuri"></a>ListenUri  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der URI, der vom Endpunkt zum Abhören verwendet wird.  
  
### <a name="name"></a>Name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der eindeutige Name des Endpunkts.  
  
### <a name="processid"></a>ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess-ID des Prozesses, von dem der Endpunkt gehostet wird.  
  
### <a name="ref"></a>ref  
 Datentyp: Contract  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
