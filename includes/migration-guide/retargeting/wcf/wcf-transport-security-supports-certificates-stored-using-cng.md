---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614498"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden

#### <a name="details"></a>Details

Von Apps für die Zielplattform .NET Framework 4.6.2 an unterstützt WCF-Transportsicherheit Zertifikate, die mithilfe der Windows-Kryptographiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn eine Anwendung auf .NET Framework 4.6.2 ausgerichtet ist, ist dieses Feature standardmäßig aktiviert. In früheren Versionen von .NET Framework löst der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicheranbieter zu verwenden, eine Ausnahme aus.

#### <a name="suggestion"></a>Vorschlag

Apps für die Zielplattform .NET Framework 4.6.1 und früher, die unter .NET Framework 4.6.2 ausgeführt werden, können Unterstützung für CNG-Zertifikate aktivieren, indem sie dem `<runtime>`-Abschnitt der app.config- oder der web.config-Datei die folgende Zeile hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

Dies kann mithilfe des folgenden Codes auch programmgesteuert erfolgen:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

Beachten Sie, dass aufgrund dieser Änderung jeglicher Code zur Ausnahmebehandlung, der von dem Versuch zur Einleitung von sicherer Kommunikation mit einem CNG-Zertifikat abhängt, nicht ausgeführt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |
