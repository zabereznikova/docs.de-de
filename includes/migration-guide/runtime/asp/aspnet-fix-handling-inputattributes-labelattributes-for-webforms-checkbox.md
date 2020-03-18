---
ms.openlocfilehash: ea0e1583cd611a624cf2d2edf9defb2294eb89d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802709"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>Behandlung von Korrekturen in ASP.NET bei InputAttributes und LabelAttributes für WebForms CheckBox-Steuerelemente

|   |   |
|---|---|
|Details|Bei Anwendungen, die .NET Framework 4.7.2 und frühere Versionen nutzen, gehen <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, die einem WebForms <xref:System.Web.UI.WebControls.CheckBox>-Steuerelement programmgesteuert hinzugefügt wurden, nach einem Postback verloren. Bei Anwendungen, die .NET Framework 4.8 oder höhere Versionen verwenden, bleiben sie nach einem Postback erhalten.|
|Vorschlag|Wenn Sie bei der Wiederherstellung nach einem Postback das richtige Verhalten erzielen möchten, legen Sie <code>targetFrameworkVersion</code> auf 4.8 oder höher fest. Beispiel:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Wenn Sie eine frühere oder gar keine Version angeben, wird das alte falsche Verhalten beibehalten.|
|`Scope`|Unbekannt|
|Version|4.8|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
