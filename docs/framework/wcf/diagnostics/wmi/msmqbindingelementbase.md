---
title: "MsmqBindingElementBase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# MsmqBindingElementBase
MsmqBindingElementBase  
  
## Syntax  
  
```  
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
  
## Methoden  
 Die Klasse MsmqBindingElementBase definiert keine Methoden.  
  
## Eigenschaften  
 Die Klasse MsmqBindingElementBase verfügt über die folgenden Eigenschaften:  
  
### CustomDeadLetterQueue  
 Datentyp: Zeichenfolge  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein URI, der den Speicherort der Warteschlange für unzustellbare Nachrichten für jede Anwendung enthält, in der Nachrichten platziert werden, die abgelaufen sind oder für die die Übertragung oder Zustellung fehlgeschlagen ist.  
  
### DeadLetterQueue  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Enumerationswert, der den Typ der zu verwendenden Warteschlange für unzustellbare Meldungen angibt.  
  
### Durable  
 Datentyp: Boolescher Wert  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten permanent oder flüchtig sind.  
  
### ExactlyOnce  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob die von dieser Bindung verarbeiteten Nachrichten genau einmal empfangen werden.  
  
### MaxRetryCycles  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl der Neuversuche für die Zustellung von Nachrichten an die empfangende Anwendung.  
  
### ReceiveErrorHandling  
 Datentyp: string \(Zeichenfolge\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Einstellungen für die Warteschlange für potenziell schädliche Nachrichten.  
  
### ReceiveRetryCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von unmittelbaren Wiederholungsversuchen auf einer Nachricht, die aus der Anwendungswarteschlange gelesen wird.  
  
### RetryCycleDelay  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein Wert, der die Zeitverzögerung zwischen den Wiederholungszyklen beim Versuch, eine Nachricht zuzustellen, die nicht sofort zugestellt werden konnte, angibt.  
  
### TimeToLive  
 Datentyp: Zeitpunkt \(Datum und Uhrzeit\)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, das angibt, wie lange die von dieser Bindung verarbeiteten Nachrichten in der Warteschlange bleiben können, bevor sie ablaufen.  
  
### UseMsmqTracing  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichten nachverfolgt werden sollen.  
  
### UseSourceJournal  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichtenkopien in der Quelljournalwarteschlange gespeichert werden sollen.  
  
## Voraussetzungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-------------------------------------|  
|Namespace|Definiert in root\\ServiceModel|  
  
## Siehe auch  
 <xref:System.ServiceModel.NetMsmqBinding>   
 <xref:System.ServiceModel.MsmqBindingBase>