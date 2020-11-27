---
title: Endpunkt
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288813"
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
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Ruft den Instanznamen des Vorgangsleistungsindikators ab.|  
  
## <a name="properties"></a>Eigenschaften  

 Die Endpoint-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="address"></a>Adresse  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der die Adresse des Endpunkts enthält.  
  
### <a name="addressheaders"></a>AddressHeaders  

 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Auflistung von Adressheadern, die diesem Endpunkt angefügt sind.  
  
### <a name="addressidentity"></a>AddressIdentity  

 Datentyp: String  
  
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden.  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Instanzname der Leistungsindikatoren des Endpunkts.  
  
### <a name="listenuri"></a>ListenUri  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der URI, der vom Endpunkt zum Abhören verwendet wird.  
  
### <a name="name"></a>Name  

 Datentyp: String  
  
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
