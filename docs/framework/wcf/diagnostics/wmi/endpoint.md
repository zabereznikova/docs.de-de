---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795908"
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
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Ruft den Instanznamen des Vorgangsleistungsindikators ab.|  
  
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
 Datentyp: Vertrag  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vertrag, der von diesem Endpunkt verfügbar gemacht wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
