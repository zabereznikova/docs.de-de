---
title: 'Breaking Change: Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759430"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: Die Typen JSObjectReference und JSInProcessObjectReference wurden in „internal“ geändert

Die neuen Typen `Microsoft.JSInterop.JSObjectReference` und `Microsoft.JSInterop.JSInProcessObjectReference`, die in ASP.NET Core 5.0 RC1 eingeführt wurden, wurden als `internal` gekennzeichnet.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

## <a name="old-behavior"></a>Altes Verhalten

`JSObjectReference` kann über `IJSRuntime` über einen JavaScript-Interop-Befehl abgerufen werden. Beispiel:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a>Neues Verhalten

`JSObjectReference` verwendet den Zugriffsmodifizierer [internal](../../../../csharp/language-reference/keywords/internal.md). Stattdessen muss die `public` `IJSObjectReference`-Schnittstelle verwendet werden. Beispiel:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` wurde ebenfalls als `internal` gekennzeichnet und durch `IJSInProcessObjectReference` ersetzt.

## <a name="reason-for-change"></a>Grund für die Änderung

Durch die Änderung wird das JavaScript-Interop-Feature mit anderen Mustern in Blazor vereinheitlicht. `IJSObjectReference` ist analog zu `IJSRuntime`, da beide Objekte einen ähnlichen Zweck erfüllen und ähnliche Methoden und Erweiterung umfassen.

## <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie `JSObjectReference` durch `IJSObjectReference` und `JSInProcessObjectReference` durch `IJSInProcessObjectReference`.

## <a name="affected-apis"></a>Betroffene APIs

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
