---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5387e197cdf26a393ba23fd5696eb095dfd17a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="callbackbehavior"></a>CallbackBehavior
CallbackBehavior  
  
## <a name="syntax"></a>Syntax  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Klasse CallbackBehavior definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse CallbackBehavior verfügt über die folgenden Eigenschaften:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Bei true wird die Sitzung automatisch geschlossen, wenn ein Dienst eine Duplexsitzung schließt.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Datentyp: string (Zeichenfolge)  
Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob unbekannte Serialisierungsdaten auf das Kabel gesendet werden sollen.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Bei Aktivierung werden den Fehlern, die an den Dienst zurückgegeben werden, Details über Ausnahmen des Rückrufs angefügt.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der aktuelle Synchronisierungskontext verwendet werden soll, um den Ausführungsthread auszuwählen.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
