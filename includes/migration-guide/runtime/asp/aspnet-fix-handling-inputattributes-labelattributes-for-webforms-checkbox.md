---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621975"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Behandlung von Korrekturen in ASP.NET bei InputAttributes und LabelAttributes für WebForms CheckBox-Steuerelemente

#### <a name="details"></a>Details

Bei Anwendungen, die .NET Framework 4.7.2 und frühere Versionen nutzen, gehen <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, die einem WebForms <xref:System.Web.UI.WebControls.CheckBox>-Steuerelement programmgesteuert hinzugefügt wurden, nach einem Postback verloren. Bei Anwendungen, die .NET Framework 4.8 oder höhere Versionen verwenden, bleiben sie nach einem Postback erhalten.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie bei der Wiederherstellung nach einem Postback das richtige Verhalten erzielen möchten, legen Sie <code>targetFrameworkVersion</code> auf 4.8 oder höher fest. Zum Beispiel:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Wenn Sie eine frühere oder gar keine Version angeben, wird das alte falsche Verhalten beibehalten.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Unbekannt|
|Version|4.8|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
