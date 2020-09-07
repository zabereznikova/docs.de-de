---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496211"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen

#### <a name="details"></a>Details

Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen. Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.

#### <a name="suggestion"></a>Vorschlag

Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen. Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
