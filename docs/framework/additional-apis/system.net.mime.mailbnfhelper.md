---
title: Mailbnfhelper-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990450"
---
# <a name="mailbnfhelper-class"></a>Mailbnfhelper-Klasse

Enthält Hilfsprogrammmethoden zum Übermitteln von Internet Nachrichten formatierten Zeichen folgen. Diese Klasse kann nicht vererbt werden.

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="ascii7bitmaxvalue-field"></a>Ascii7bitMaxValue-Feld

Stellt den maximalen 7-Bit-ASCII-Wert dar.

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a>ATEXT-Feld

Stellt die Zeichen dar, die in Atomen zulässig sind.

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a>CR-Feld

Stellt das Wagen Rücklauf Zeichen dar.

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a>CTEXT-Feld

Stellt die Zeichen dar, die innerhalb von Kommentaren zulässig sind.

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a>Punktfeld

Stellt das vollendezeichen ( `.` ) dar.

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a>EndComment-Feld

Stellt das Zeichen dar, das das Ende eines Kommentars angibt.

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a>LF-Feld

Stellt das Zeilenvorschub Zeichen dar.

```csharp
internal static readonly char LF
```

## <a name="space-field"></a>Feld "Space"

Stellt das Leerzeichen dar.

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a>StartComment-Feld

Stellt das Zeichen dar, das den Anfang eines Kommentars angibt.

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a>Registerkarten Feld

Stellt das Tabstopp Zeichen dar.

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
