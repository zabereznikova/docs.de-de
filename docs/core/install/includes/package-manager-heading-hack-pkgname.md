---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506862"
---

Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.

- **Produkt**\
Der Typ des zu installierenden .NET-Produkts. Folgende Optionen sind gültig:

  - dotnet
  - aspnetcore

- **Typ**\
Wählt das SDK oder die Runtime aus. Folgende Optionen sind gültig:

  - SDK
  - Laufzeit

- **Version**\
Die Version des zu installierenden SDK oder der zu installierenden Runtime. In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version. Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:

  - 5.0
  - 3.1
  - 3.0
  - 2.1

  Es ist möglich, dass das SDK bzw. die Runtime, das/die Sie herunterladen möchten, für Ihre Linux-Distribution nicht verfügbar ist. Eine Liste der unterstützten Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../linux.md).

### <a name="examples"></a>Beispiele

- Installieren der ASP.NET Core 5.0-Runtime: `aspnetcore-runtime-5.0`
- Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`
- Installieren des .NET 5.0 SDK: `dotnet-sdk-5.0`
- Installieren des .NET Core 3.1 SDK: `dotnet-sdk-3.1`

### <a name="package-missing"></a>Fehlendes Paket

Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar. Beispielsweise gibt es kein ASP.NET Core SDK, die SDK-Komponenten sind im .NET SDK enthalten. Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten. Eine Liste der von .NET Core unterstützten Linux-Distributionen finden Sie unter [.NET-Abhängigkeiten und -Anforderungen](../linux.md).
