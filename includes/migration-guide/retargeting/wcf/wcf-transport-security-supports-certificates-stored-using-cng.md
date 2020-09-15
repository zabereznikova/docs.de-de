---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614498"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a><span data-ttu-id="9fb5b-101">Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden</span><span class="sxs-lookup"><span data-stu-id="9fb5b-101">WCF transport security supports certificates stored using CNG</span></span>

#### <a name="details"></a><span data-ttu-id="9fb5b-102">Details</span><span class="sxs-lookup"><span data-stu-id="9fb5b-102">Details</span></span>

<span data-ttu-id="9fb5b-103">Von Apps für die Zielplattform .NET Framework 4.6.2 an unterstützt WCF-Transportsicherheit Zertifikate, die mithilfe der Windows-Kryptographiebibliothek (CNG) gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-103">Starting with apps that target the .NET Framework 4.6.2, WCF transport security supports certificates stored using the Windows Cryptography Library (CNG).</span></span> <span data-ttu-id="9fb5b-104">Diese Unterstützung ist auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-104">This support is limited to certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="9fb5b-105">Wenn eine Anwendung auf .NET Framework 4.6.2 ausgerichtet ist, ist dieses Feature standardmäßig aktiviert. In früheren Versionen von .NET Framework löst der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicheranbieter zu verwenden, eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-105">When an application targets the .NET Framework 4.6.2, this feature is on by default.In earlier versions of the .NET Framework, the attempt to use X509 certificates with a CSG key storage provider throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fb5b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9fb5b-106">Suggestion</span></span>

<span data-ttu-id="9fb5b-107">Apps für die Zielplattform .NET Framework 4.6.1 und früher, die unter .NET Framework 4.6.2 ausgeführt werden, können Unterstützung für CNG-Zertifikate aktivieren, indem sie dem `<runtime>`-Abschnitt der app.config- oder der web.config-Datei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9fb5b-107">Apps that target the .NET Framework 4.6.1 and earlier but are running on the .NET Framework 4.6.2 can enable support for CNG certificates by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

<span data-ttu-id="9fb5b-108">Dies kann mithilfe des folgenden Codes auch programmgesteuert erfolgen:</span><span class="sxs-lookup"><span data-stu-id="9fb5b-108">This can also be done programmatically with the following code:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="9fb5b-109">Beachten Sie, dass aufgrund dieser Änderung jeglicher Code zur Ausnahmebehandlung, der von dem Versuch zur Einleitung von sicherer Kommunikation mit einem CNG-Zertifikat abhängt, nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9fb5b-109">Note that, because of this change, any exception handling code that depends on the attempt to initiate secure communication with a CNG certificate to fail will no longer execute.</span></span>

| <span data-ttu-id="9fb5b-110">name</span><span class="sxs-lookup"><span data-stu-id="9fb5b-110">Name</span></span>    | <span data-ttu-id="9fb5b-111">Wert</span><span class="sxs-lookup"><span data-stu-id="9fb5b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fb5b-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="9fb5b-112">Scope</span></span>   | <span data-ttu-id="9fb5b-113">Gering</span><span class="sxs-lookup"><span data-stu-id="9fb5b-113">Minor</span></span>       |
| <span data-ttu-id="9fb5b-114">Version</span><span class="sxs-lookup"><span data-stu-id="9fb5b-114">Version</span></span> | <span data-ttu-id="9fb5b-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9fb5b-115">4.6.2</span></span>       |
| <span data-ttu-id="9fb5b-116">Typ</span><span class="sxs-lookup"><span data-stu-id="9fb5b-116">Type</span></span>    | <span data-ttu-id="9fb5b-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="9fb5b-117">Retargeting</span></span> |
