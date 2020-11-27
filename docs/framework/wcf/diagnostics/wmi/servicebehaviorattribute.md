---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: e3716d42d479bcbdfd900b4fd2e335576a71574b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295599"
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute

ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die ServiceBehaviorAttribute-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die ServiceBehaviorAttribute-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob eine Sitzung automatisch geschlossen werden soll, wenn ein Client eine Ausgabesitzung schließt.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  

 Datentyp: String  
Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ein Dienst einen Thread, mehrere Threads oder wiedereintrittsfähige Aufrufe unterstützt.  
  
### <a name="configurationname"></a>ConfigurationName  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name der Dienstkonfiguration.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob unbekannte Serialisierungsdaten gesendet werden sollen.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, wann ein neues Dienstobjekt erstellt wird.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von in einem serialisierten Objekt zugelassenen Elementen.  
  
### <a name="name"></a>Name  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Namensattribut des Diensts in WSDL.  
  
### <a name="namespace"></a>Namespace  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zielnamespace des Diensts in WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob das Dienstobjekt wiederverwendet wird, wenn die aktuelle Transaktion abgeschlossen wird.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die aktuelle Sitzung schließt.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Bestimmt die Isolationsstufe für die Transaktionen.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  

 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Zeitraum, in dem eine Transaktion abgeschlossen werden muss.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob der aktuelle Synchronisierungskontext zur Auswahl der Threadausführung verwendet werden soll.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt fest, ob das System oder die Anwendung die Verarbeitung von SOAP MustUnderstand-Headern erzwingt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
