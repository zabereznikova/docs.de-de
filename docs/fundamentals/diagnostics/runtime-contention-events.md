---
title: Lauf Zeit Ereignisse für Sperr Konflikte überwachen
description: Weitere Informationen zu den Monitor Sperr Konflikten finden Sie unter ETW-Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592084"
---
# <a name="net-runtime-contention-events"></a>.Net-Lauf Zeit konfliktereignisse

Diese Lauf Zeit Ereignisse erfassen Informationen zu Monitor Sperr Konflikten wie z `Monitor.Enter` . b. mit oder dem c#-Schlüsselwort Lock. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="contentionstart_v1-event"></a>ContentionStart_V1 Ereignis

Dieses Ereignis wird zu Beginn eines Monitor Sperr Konflikts ausgegeben.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Ein Monitor Sperr Konflikt wird gestartet.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` für verwaltete; `1` für nativ.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="contentionstop_v1-event"></a>ContentionStop_V1 Ereignis

Dieses Ereignis wird am Ende eines Monitor Sperr Konflikts ausgegeben.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|91|Ein Monitor Sperr Konflikt wird beendet.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` für verwaltete; `1` für nativ.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
|`DurationNs`|`win:Double`|Die Dauer des Konflikts in Nanosekunden.|
