---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da0bc2ac9a4283ec9b23a1d4767f664de071ef47
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 <xref:System.ServiceModel.OperationBehaviorAttribute>
