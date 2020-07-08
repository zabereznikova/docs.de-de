---
title: Mailadressssparser-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051349"
---
# <a name="mailaddressparser-class"></a>MailAddressParser-Klasse

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
