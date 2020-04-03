---
ms.openlocfilehash: 4340ed7444681b4601dea50c93926b0ee0c07eec
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134112"
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

  - 3.1
  - 3.0
  - 2.1

  Es ist möglich, dass das SDK bzw. die Runtime, das/die Sie herunterladen möchten, für Ihre Linux-Distribution nicht verfügbar ist. Eine Liste der unterstützten Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../dependencies.md?pivots=os-linux).

### <a name="examples"></a>Beispiele

- Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`
- Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`
- Installieren des .NET Core 3.1 SDK: `dotnet-sdk-3.1`

### <a name="package-missing"></a>Fehlendes Paket

Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar. Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten. Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten. Eine Liste der von .NET Core unterstützten Linux-Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../dependencies.md?pivots=os-linux).
