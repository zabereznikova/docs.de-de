---
ms.openlocfilehash: 7444ddbdd4a7c5f731fba8528ee2334374fc254e
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275118"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen

|   |   |
|---|---|
|Details|Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen. Während <code>/controller/action/some data</code> zuvor mit der Route <code>/controller/action/{data}</code> übereinstimmte und <code>some data</code> als Datenparameter bereitgestellt wurde, stellt sie daher jetzt <code>some%20data</code> bereit.|
|Vorschlag|Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen. Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString-API darauf zugegriffen werden.|
|`Scope`|Nebenversion|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
