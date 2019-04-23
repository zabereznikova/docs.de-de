---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 1df4b32feda246a536183a42ac11b113bc4bb259
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768396"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Klasse MsmqBindingElementBase definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse MsmqBindingElementBase verfügt über die folgenden Eigenschaften:  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der den Speicherort der Warteschlange für unzustellbare Nachrichten für jede Anwendung enthält, in der Nachrichten platziert werden, die abgelaufen sind oder für die die Übertragung oder Zustellung fehlgeschlagen ist.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Enumerationswert, der den Typ der zu verwendenden Warteschlange für unzustellbare Meldungen angibt.  
  
### <a name="durable"></a>Durable  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten permanent oder flüchtig sind.  
  
### <a name="exactlyonce"></a>ExactlyOnce  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten genau einmal empfangen werden.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl der Neuversuche für die Zustellung von Nachrichten an die empfangende Anwendung.  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Einstellungen für die Warteschlange für potenziell schädliche Nachrichten.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von unmittelbaren Wiederholungsversuchen auf einer Nachricht, die aus der Anwendungswarteschlange gelesen wird.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der die Zeitverzögerung zwischen den Wiederholungszyklen beim Versuch, eine Nachricht zuzustellen, die nicht sofort zugestellt werden konnte, angibt.  
  
### <a name="timetolive"></a>TimeToLive  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das angibt, wie lange die von dieser Bindung verarbeiteten Nachrichten in der Warteschlange bleiben können, bevor sie ablaufen.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichten nachverfolgt werden sollen.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichtenkopien in der Quelljournalwarteschlange gespeichert werden sollen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
