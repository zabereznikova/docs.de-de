---
title: Unsafenclnativemethods-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990447"
---
# <a name="unsafenclnativemethods-class"></a>Unsafenclnativemethods-Klasse

Enthält Klassen, die unsichere Native Netzwerk Methoden importieren. Diese Klasse kann nicht vererbt werden.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.

## <a name="nativepki-class"></a>Nativepki-Klasse

Enthält Methoden, die aus crypt32.dll importiert wurden. Diese Methoden behandeln Zertifikate bei der Verwendung von Hypertext Transfer Protocol Secure (HTTPS). Diese Klasse kann nicht vererbt werden.

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a>Nativepki. findclientzertifikate-Methode

Ermittelt verfügbare Client Zertifikate, die an den Server gesendet werden sollen.

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a>Rückgabewert

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

Eine Sammlung verfügbarer Client Zertifikate.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.Net>

**Assembly:** System (in System.dll)
