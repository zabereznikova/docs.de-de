---
title: Quotedpaarreader-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051310"
---
# <a name="quotedpairreader-class"></a>QuotedPairReader-Klasse

Bestimmt, welche Zeichen in einer Zeichenfolge in Anführungszeichen (mit Escapezeichen) angegeben werden Diese Klasse kann nicht vererbt werden.

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="countquotedchars-method"></a>Countrytquotedchars-Methode

Zählt die Anzahl der aufeinander folgenden Zeichen in Anführungszeichen, einschließlich mehrerer vorangehender umgekehrter Schrägstriche in der angegebenen Zeichenfolge. Wenn beispielsweise die Zeichenfolge `a\\\b` und ein Index von angegeben werden `4` , gibt die Methode zurück, da in Anführungszeichen eingeschlossen `4` `b` ist und die drei vorangehenden umgekehrten Schrägstriche sind.

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a>Parameter

- `data` <xref:System.String>

  Die Daten Zeichenfolge, in der aufeinanderfolgende Anführungszeichen gezählt werden sollen.

- `index` <xref:System.Int32>

  Die Position in der angegebenen Zeichenfolge bis zu und einschließlich der aufeinander folgenden Zeichen, die gezählt werden sollen.

- `permitUnicodeEscaping` <xref:System.Boolean>

  `true`, um das Escapezeichen von Unicode-Zeichen zuzulassen. andernfalls `false` .

### <a name="return-value"></a>Rückgabewert

<xref:System.Int32?displayProperty=nameWithType>

`0`, wenn das Zeichen am angegebenen Index nicht mit Escapezeichen versehen ist. andernfalls die Anzahl der aufeinander folgenden Zeichen in Anführungszeichen bis einschließlich des Zeichens bei `index` .

### <a name="exceptions"></a>Ausnahmen

<xref:System.FormatException?displayProperty=nameWithType>

Ein Escapezeichen mit Escapezeichen wurde gefunden, ist aber nicht zulässig.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
