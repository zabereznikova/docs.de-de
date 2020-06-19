---
title: Logging-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990475"
---
# <a name="logging-class"></a>Logging-Klasse

Bietet Funktionen für die Ablauf Verfolgungs Protokollierung

```csharp
internal class Logging
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="associate-method"></a>Methode zuordnen

Protokolliert Informationen, die zwei-Objekten zugeordnet sind.

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `objA` <xref:System.Object>

  Das Objekt, das zugeordnet werden soll `objB` .

- `objB` <xref:System.Object>

  Das Objekt, das zugeordnet werden soll `objA` .

## <a name="entertracesource-object-string-string-method"></a>Enter (TraceSource, Object, String, String)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.Object>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die eingegeben wird.

- `param` <xref:System.String>

  Die Parameter, die an die-Methode übermittelt wurden.

## <a name="entertracesource-object-string-object-method"></a>Enter (TraceSource, Object, String, Object)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.Object>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die eingegeben wird.

- `paramObject` <xref:System.Object>

  Die Parameter, die an die-Methode übermittelt wurden.

## <a name="entertracesource-string-string-string-method"></a>Enter (TraceSource, String, String, String)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.String>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die eingegeben wird.

- `param` <xref:System.String>

  Die Parameter, die an die-Methode übermittelt wurden.

## <a name="entertracesource-string-string-object-method"></a>Enter (TraceSource, String, String, Object)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.String>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die eingegeben wird.

- `paramObject` <xref:System.Object>

  Die Parameter, die an die-Methode übermittelt wurden.

## <a name="entertracesource-string-string-method"></a>Enter (TraceSource, String, String)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `method` <xref:System.String>

  Die Methode, die eingegeben wird.

- `parameters` <xref:System.String>

  Die Parameter, die an die-Methode übermittelt wurden.

## <a name="entertracesource-string-method"></a>Enter (TraceSource, String)-Methode

Protokolliert den Eingang einer Methode.

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `msg` <xref:System.String>

  Die Eingangs Nachricht, die an der Ablauf Verfolgungs Quelle protokolliert werden soll.

## <a name="exception-method"></a>Exception-Methode

Protokolliert eine Ausnahme und stellt den Einzug wieder her.

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.Object>

  Das-Objekt, für das die Methode, die eine Ausnahme ausgelöst hat, aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die die Ausnahme ausgelöst hat.

- `e` <xref:System.Exception>

  Die ausgelöste Ausnahme.

## <a name="exittracesource-object-string-object-method"></a>Exit (TraceSource, Object, String, Object)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.Object>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die beendet wird.

- `retObject` <xref:System.Object>

  Der Wert, der von der-Methode zurückgegeben wird.

## <a name="exittracesource-string-string-object-method"></a>Exit (TraceSource, String, String, Object)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.String>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die beendet wird.

- `retObject` <xref:System.Object>

  Der Wert, der von der-Methode zurückgegeben wird.

## <a name="exittracesource-object-string-string-method"></a>Exit (TraceSource, Object, String, String)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.Object>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die beendet wird.

- `retValue` <xref:System.String>

  Der Wert, der von der-Methode zurückgegeben wird.

## <a name="exittracesource-string-string-string-method"></a>Exit (TraceSource, String, String, String)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `obj` <xref:System.String>

  Das-Objekt, für das die-Methode aufgerufen wurde.

- `method` <xref:System.String>

  Die Methode, die beendet wird.

- `retValue` <xref:System.String>

  Der Wert, der von der-Methode zurückgegeben wird.

## <a name="exittracesource-string-string-method"></a>Exit (TraceSource, String, String)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `method` <xref:System.String>

  Die Methode, die beendet wird.

- `parameters` <xref:System.String>

  Die Parameter, die an die Methode, die beendet wird, übermittelt wurden.

## <a name="exittracesource-string-method"></a>Exit (TraceSource, String)-Methode

Protokolle werden aus einer Funktion beendet.

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Parameter

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Die Ablauf Verfolgungs Quelle, in der das Ereignis protokolliert werden soll.

- `msg` <xref:System.String>

  Die Exit-Meldung, die an die Ablauf Verfolgungs Quelle protokolliert werden soll.

## <a name="http-property"></a>Http-Eigenschaft

Ruft die Ablauf Verfolgungs Quelle für "System .net. http" ab.

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a>Eigenschaftswert

<xref:System.Diagnostics.TraceSource>\
Die Ablauf Verfolgungs Quelle für "System .net. http" oder, `null` Wenn die Protokollierung nicht aktiviert ist.

## <a name="on-property"></a>On-Eigenschaft

Ruft einen Wert ab, der angibt, ob die Protokollierung aktiviert ist.

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a>Eigenschaftswert

<xref:System.Boolean>\
`true`, wenn die Protokollierung aktiviert ist, andernfalls `false`.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
