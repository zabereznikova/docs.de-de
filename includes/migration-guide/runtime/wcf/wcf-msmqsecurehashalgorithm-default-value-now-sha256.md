---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621221"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF. In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.

#### <a name="suggestion"></a>Vorschlag

Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.7.1|
|Typ|Laufzeit|
