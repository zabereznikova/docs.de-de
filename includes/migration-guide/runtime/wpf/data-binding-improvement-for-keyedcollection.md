---
ms.openlocfilehash: a0dc2401155a162eaa5aa6b4d9e6af1ca1c2ccc8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802574"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="b9309-101">Verbesserung der Datenbindung für KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="b9309-101">Data Binding improvement for KeyedCollection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9309-102">Details</span><span class="sxs-lookup"><span data-stu-id="b9309-102">Details</span></span>|<span data-ttu-id="b9309-103">Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.</span><span class="sxs-lookup"><span data-stu-id="b9309-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (e.g. KeyedCollection&lt;int,TItem&gt;).</span></span>|
|<span data-ttu-id="b9309-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b9309-104">Suggestion</span></span>|<span data-ttu-id="b9309-105">Damit die Anwendung von dieser Änderung profitiert, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="b9309-105">In order for the application to benefit from this change, it must run on the .NET Framework 4.7.2 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b9309-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="b9309-106">Scope</span></span>|<span data-ttu-id="b9309-107">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="b9309-107">Major</span></span>|
|<span data-ttu-id="b9309-108">Version</span><span class="sxs-lookup"><span data-stu-id="b9309-108">Version</span></span>|<span data-ttu-id="b9309-109">4.8</span><span class="sxs-lookup"><span data-stu-id="b9309-109">4.8</span></span>|
|<span data-ttu-id="b9309-110">Typ</span><span class="sxs-lookup"><span data-stu-id="b9309-110">Type</span></span>|<span data-ttu-id="b9309-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b9309-111">Runtime</span></span>|

