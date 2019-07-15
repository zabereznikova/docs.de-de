---
ms.openlocfilehash: 745e880db08c5fa7e5514a71758f7fbb042e7ef4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858953"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>SHA256 ist jetzt der Standardhashalgorithmus für WPF-PackageDigitalSignatureManager

|   |   |
|---|---|
|Details|Der <code>System.IO.Packaging.PackageDigitalSignatureManager</code> stellt Funktionen zur digitalen Signatur von WPF-Paketen zur Verfügung.  In .NET Framework 4.7 und früheren Versionen, war SHA1 der Standardhashalgorithmus (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>), der zum Signieren von Paketbestandteilen verwendet wurde.  Diese Standardeinstellung wurde ab .NET Framework 4.7.1 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 auf SHA256 geändert.  Diese Änderung betrifft die Signierung aller Pakete, einschließlich XPS-Dokumenten.|
|Vorschlag|Ein Entwickler, der diese Änderung nutzen will, aber seine Anwendung auf eine ältere Version von .NET Framework als Version 4.7.1 auslegt, oder ein Entwickler, der die veraltete Funktion verwenden möchte, seine Anwendung jedoch auf .NET Framework 4.7.1 oder höher auslegt, können das „AppContext“-Flag entsprechend festlegen.  Wenn ein TRUE-Wert zurückgegeben wird, wird SHA1 als Standardalgorithmus verwendet. Bei FALSE-Werten wird SHA256 zurückgegeben.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType></li></ul>|

