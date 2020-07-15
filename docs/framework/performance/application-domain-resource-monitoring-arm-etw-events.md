---
title: ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)
description: Informieren Sie sich über die ETW-Ereignisse der Anwendungs Domänen Ressourcenüberwachung (Arm) in .net, wie z. b. ThreadCreated, appdomainmemreserviert, appdomainmemlag und mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309780"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a>ETW-Ereignisse der Anwendungsdomänen-Ressourcenüberwachung (Application Domain Resource Monitoring, ARM)

Diese Ereignisse bieten detaillierte Diagnoseinformationen zum Status einer Anwendungsdomäne. Sie können diese Ereignisse oder die Funktion zur Überwachung von Anwendungsdomänenressourcen (ARM) verwenden, um dieselben Informationen zu erhalten.

## <a name="threadcreated-event"></a>ThreadCreated-Ereignis

Dieses Ereignis wird auch unter dem Rundownanbieter als `ThreadDC` ausgelöst (unter dem Schlüsselwort `AppDomainResourceManagementRundownKeyword` ). Dies ist das einzige Ereignis, das unter dem Rundownanbieter in dieser Kategorie ausgelöst wird.

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0x800)|Information (4)|
|`ThreadingKeyword` (0x10000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ThreadCreated`|85|Ein Thread wurde für die Anwendungsdomäne erstellt.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Die ID des Threads, der erstellt wurde.|
|AppDomainID|win:UInt64|Der Bezeichner der Anwendungsdomäne, für die die Threadaktivität gemeldet wird.|
|Flags|win:UInt32|Threaderstellungs-Flags.|
|ManagedThreadIndex|win:UInt32|Der verwaltete Index des Threads, der erstellt wurde.|
|OSThreadID|win:UInt32|Die Betriebssystem-ID des Threads, der erstellt wurde.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="appdomainmemallocated-event"></a>AppDomainMemAllocated-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0x800)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|83|Jede 4 MB des Arbeitsspeichers (ungefähr) werden in der Anwendungsdomäne zugeordnet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|AppDomainID|win:UInt64|Der Bezeichner der Anwendungsdomäne, für den die Ressourcenauslastung gemeldet wird.|
|Zugeordnet|win:UInt64|Die Gesamtzahl von Bytes, die in dieser Anwendungsdomäne seit ihrer Erstellung zugeordnet wurden (die Menge des freigegebenen Speichers wird nicht abgezogen).|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="appdomainmemsurvived-event"></a>AppDomainMemSurvived-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0x800)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|84|Jede Garbage Collection wurde beendet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|AppDomainID|win:UInt64|Der Bezeichner der Domäne, für den die Ressourcenauslastung gemeldet wird.|
|Survived|win:UInt64|Die Anzahl von Bytes, die nach der letzten Auflistung noch vorhanden sind und die bekanntermaßen von dieser Anwendungsdomäne aufgenommen werden. Diese Anzahl ist genau und nach einer vollständigen Auflistung abgeschlossen, aber nach einer kurzlebiger Auflistung unvollständig.|
|ProcessSurvived|win:UInt64|Die Gesamtanzahl der Bytes, die seit der letzten Auflistung noch vorhanden sind. Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps live gespeichert werden. Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen live gespeichert werden.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadappdomainenter-event"></a>ThreadAppDomainEnter-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0x800)|Information (4)|
|`ThreadingKeyword` (0x10000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|87|Ein Thread wechselt in eine Anwendungsdomäne.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Der Threadbezeichner.|
|AppDomainID|win:UInt64|Der Bezeichner der Anwendungsdomäne.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="threadterminated-event"></a>ThreadTerminated-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0x800)|Information (4)|
|`ThreadingKeyword` (0x10000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ThreadTerminated`|86|Ein Thread wird beendet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Der Threadbezeichner.|
|AppDomainID|win:UInt64|Der Bezeichner der Anwendungsdomäne.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
