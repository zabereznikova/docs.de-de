---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04a5cb87b9ed61fd278ce0f2e05e5f1c954de5b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="contract"></a>Vertrag
Vertrag  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
### <a name="name"></a>name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vertrags in WSDL.  
  
### <a name="namespace"></a>Namespace  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des `portType`-Elements in WSDL.  
  
### <a name="operations"></a>Vorgänge  
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
 <xref:System.ServiceModel.Description.ContractDescription>
