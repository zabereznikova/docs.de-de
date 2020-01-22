---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116148"
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

  - 3.0
  - 2.2
  - 2.1

### <a name="examples"></a>Beispiele

- Installieren des .NET Core 2.2 SDK: `dotnet-sdk-2.2`
- Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`
- Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`

### <a name="troubleshoot"></a>Problembehandlung

Wenn die Paketkombination nicht funktioniert, ist sie nicht verfügbar. Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten. Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.
