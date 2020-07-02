---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621210"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Entfernen von „Ssl3“ aus der WCF-Klasse „TransportDefaults“

#### <a name="details"></a>Details

Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird das SSL3-Protokoll nicht mehr als eins der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet. In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 schon immer in der Protokollliste für „NetTcp“ enthalten ist. Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.

#### <a name="suggestion"></a>Vorschlag

Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um Ssl3 der Liste der ausgehandelten Protokolle hinzuzufügen.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6.2|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
