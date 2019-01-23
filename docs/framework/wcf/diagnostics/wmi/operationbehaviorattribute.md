---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504326"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die OperationBehaviorAttribute-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die OperationBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zustand der Funktion für automatisches Verwerfen für Parameter.  
  
### <a name="impersonation"></a>Identitätswechsel  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Ebene des Aufruferidentitätswechsels an, die von dem Vorgang unterstützt wird.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, wann das Objekt im Verlauf eines Vorgangsaufrufs wiederverwendet werden soll.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die aktuelle Transaktion automatisch übergeben werden soll, wenn keine unbehandelten Ausnahmen auftreten.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der Vorgang eine Transaktion erfordert.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.OperationBehaviorAttribute>
