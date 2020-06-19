---
title: Mailadressssparser-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.MailAddressParser
- System.Net.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 2c17970614ff9b6f1e6793a064a956da7248d693
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990455"
---
# <a name="mailaddressparser-class"></a>Mailadressssparser-Klasse

Analysiert e-Mail-Adressen, wie in RFC 2822 beschrieben. Diese Klasse kann nicht vererbt werden.

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="parseaddress-method"></a>Methode "samanaddress"

Analysiert eine einzelne e-Mail-Adresse aus der angegebenen Zeichenfolge.

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a>Parameter

`data` <xref:System.String>

Die Zeichenfolge, die eine e-Mail-Adresse enthält, die analysiert werden soll.

### <a name="return-value"></a>Rückgabewert

<xref:System.Net.Mail.MailAddress>

Eine gültige e-Mail-Adresse.

### <a name="exceptions"></a>Ausnahmen

<xref:System.FormatException?displayProperty=nameWithType>

Die e-Mail-Adresse ist ungültig.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
