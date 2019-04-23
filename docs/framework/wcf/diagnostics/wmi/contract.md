---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772998"
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
 Datentyp: Behavior-array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die mit diesem Vertrag verknüpften Verhalten.  
  
### <a name="name"></a>Name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vertrags in WSDL.  
  
### <a name="namespace"></a>Namespace  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des `portType`-Elements in WSDL.  
  
### <a name="operations"></a>Vorgänge  
 Datentyp: Operation-array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Vorgang dieses Vertrags.  
  
### <a name="processid"></a>ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Porzess-ID des Prozesses, der den Vertrag hostet.  
  
### <a name="ref"></a>ref  
 Datentyp: Vertrag  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Rückrufs, wenn es sich beim Vertrag um einen Duplexvertrag handelt.  
  
### <a name="sessionmode"></a>SessionMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der Vertrag die ihm zugeordnete Bindung für die Verwendung der Kanalsitzung benötigt.  
  
### <a name="type"></a>Typ  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Typ des Vertrags.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ContractDescription>
