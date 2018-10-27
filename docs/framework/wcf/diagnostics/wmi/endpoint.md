---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452926"
---
# <a name="endpoint"></a>Endpunkt
Endpunkt  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
