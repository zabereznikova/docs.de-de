---
ms.openlocfilehash: 8964cd2f69e95e4078001997ad5a5d126ce42d7b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497782"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="0cb17-101">Verbesserung der Datenbindung für KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="0cb17-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="0cb17-102">Details</span><span class="sxs-lookup"><span data-stu-id="0cb17-102">Details</span></span>

<span data-ttu-id="0cb17-103">Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.</span><span class="sxs-lookup"><span data-stu-id="0cb17-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0cb17-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0cb17-104">Suggestion</span></span>

<span data-ttu-id="0cb17-105">Damit eine Anwendung für eine ältere Version von dieser Änderung profitiert, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="0cb17-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0cb17-106">name</span><span class="sxs-lookup"><span data-stu-id="0cb17-106">Name</span></span>    | <span data-ttu-id="0cb17-107">Wert</span><span class="sxs-lookup"><span data-stu-id="0cb17-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0cb17-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="0cb17-108">Scope</span></span>   |<span data-ttu-id="0cb17-109">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="0cb17-109">Major</span></span>|
|<span data-ttu-id="0cb17-110">Version</span><span class="sxs-lookup"><span data-stu-id="0cb17-110">Version</span></span>|<span data-ttu-id="0cb17-111">4.8</span><span class="sxs-lookup"><span data-stu-id="0cb17-111">4.8</span></span>|
|<span data-ttu-id="0cb17-112">Typ</span><span class="sxs-lookup"><span data-stu-id="0cb17-112">Type</span></span>|<span data-ttu-id="0cb17-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0cb17-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0cb17-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0cb17-114">Affected APIs</span></span>

<span data-ttu-id="0cb17-115">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="0cb17-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
