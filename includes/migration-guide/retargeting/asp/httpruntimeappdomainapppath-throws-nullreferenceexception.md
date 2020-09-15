---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617532"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath löst NullReferenceException aus

#### <a name="details"></a>Details

In .NET Framework 4.6.2 löst die Laufzeit `T:System.NullReferenceException` aus, wenn ein `P:System.Web.HttpRuntime.AppDomainAppPath`-Wert abgerufen wird, der NULL-Zeichen enthält. In .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit eine `T:System.ArgumentNullException` aus.

#### <a name="suggestion"></a>Vorschlag

Sie können mit einer der folgenden Möglichkeiten auf diese Änderung reagieren:

- Behandeln Sie die `T:System.NullReferenceException`, wenn Ihre Anwendung in .NET Framework 4.6.2 ausgeführt wird.
- Führen Sie ein Upgrade auf .NET Framework 4.7 durch, sodass das vorherige Verhalten wiederhergestellt und eine `T:System.ArgumentNullException` ausgelöst wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
