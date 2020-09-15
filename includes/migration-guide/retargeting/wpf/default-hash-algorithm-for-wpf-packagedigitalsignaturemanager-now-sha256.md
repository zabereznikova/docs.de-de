---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614585"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>SHA256 ist jetzt der Standardhashalgorithmus für WPF-PackageDigitalSignatureManager

#### <a name="details"></a>Details

Der `System.IO.Packaging.PackageDigitalSignatureManager` stellt Funktionen zur digitalen Signatur von WPF-Paketen zur Verfügung.  In .NET Framework 4.7 und früheren Versionen, war SHA1 der Standardhashalgorithmus (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>), der zum Signieren von Paketbestandteilen verwendet wurde.  Diese Standardeinstellung wurde ab .NET Framework 4.7.1 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 auf SHA256 geändert.  Diese Änderung betrifft die Signierung aller Pakete, einschließlich XPS-Dokumenten.

#### <a name="suggestion"></a>Vorschlag

Ein Entwickler, der diese Änderung nutzen will, aber seine Anwendung auf eine ältere Version von .NET Framework als Version 4.7.1 auslegt, oder ein Entwickler, der die veraltete Funktion verwenden möchte, seine Anwendung jedoch auf .NET Framework 4.7.1 oder höher auslegt, können das „AppContext“-Flag entsprechend festlegen.  Wenn ein TRUE-Wert zurückgegeben wird, wird SHA1 als Standardalgorithmus verwendet. Bei FALSE-Werten wird SHA256 zurückgegeben.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
