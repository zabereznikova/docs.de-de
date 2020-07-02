---
ms.openlocfilehash: beb869208e8d48d762d94b5989a558fa2f1aaf29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622010"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="7d3b3-101">Verbesserung der Datenbindung für KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="7d3b3-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="7d3b3-102">Details</span><span class="sxs-lookup"><span data-stu-id="7d3b3-102">Details</span></span>

<span data-ttu-id="7d3b3-103">Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.</span><span class="sxs-lookup"><span data-stu-id="7d3b3-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d3b3-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7d3b3-104">Suggestion</span></span>

<span data-ttu-id="7d3b3-105">Damit eine Anwendung für eine ältere Version von dieser Änderung profitiert, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="7d3b3-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="7d3b3-106">name</span><span class="sxs-lookup"><span data-stu-id="7d3b3-106">Name</span></span>    | <span data-ttu-id="7d3b3-107">Wert</span><span class="sxs-lookup"><span data-stu-id="7d3b3-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d3b3-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="7d3b3-108">Scope</span></span>   |<span data-ttu-id="7d3b3-109">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="7d3b3-109">Major</span></span>|
|<span data-ttu-id="7d3b3-110">Version</span><span class="sxs-lookup"><span data-stu-id="7d3b3-110">Version</span></span>|<span data-ttu-id="7d3b3-111">4.8</span><span class="sxs-lookup"><span data-stu-id="7d3b3-111">4.8</span></span>|
|<span data-ttu-id="7d3b3-112">Typ</span><span class="sxs-lookup"><span data-stu-id="7d3b3-112">Type</span></span>|<span data-ttu-id="7d3b3-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7d3b3-113">Runtime</span></span>|
