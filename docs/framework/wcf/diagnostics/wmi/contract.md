---
title: Vertrag
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 0df39bbd0b273f1e898ccbe585be288cc245b7f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274139"
---
# <a name="contract"></a>Vertrag

Vertrag  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die Contract-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die Contract-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="appdomainid"></a>AppDomainId  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Anwendungsdomänen-ID der Anwendungsdomäne, die den Vertrag hostet.  
  
### <a name="behaviors"></a>Verhalten  

 Datentyp: Behavior-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die mit diesem Vertrag verknüpften Verhalten.  
  
### <a name="name"></a>Name  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vertrags in WSDL.  
  
### <a name="namespace"></a>Namespace  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des `portType`-Elements in WSDL.  
  
### <a name="operations"></a>Operations  

 Datentyp: Operation-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vorgang dieses Vertrags.  
  
### <a name="processid"></a>ProcessId  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Porzess-ID des Prozesses, der den Vertrag hostet.  
  
### <a name="ref"></a>ref  

 Datentyp: Contract  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.  
  
### <a name="sessionmode"></a>SessionMode  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.  
  
### <a name="type"></a>type  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Vertrags.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ContractDescription>
