---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620165"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode decodiert keine ungültigen Eingabesequenzen mehr

#### <a name="details"></a>Details

Decodierungsmethoden decodieren nicht mehr standardmäßig ungültige Eingabesequenzen in ungültige UTF-16-Zeichenfolgen. Stattdessen geben sie die ursprüngliche Eingabe zurück.

#### <a name="suggestion"></a>Vorschlag

Die Änderung der Decoderausgabe sollte nur von Bedeutung sein, wenn Sie Binärdaten statt der UTF-16-Daten in Zeichenfolgen speichern. Um dieses Verhalten explizit zu steuern, legen Sie das <code>aspnet:AllowRelaxedUnicodeDecoding</code>-Attribut des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md)-Elements auf <code>true</code> fest, um Legacyverhalten zu aktivieren, oder auf <code>false</code>, um das aktuelle Verhalten zu aktivieren.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
