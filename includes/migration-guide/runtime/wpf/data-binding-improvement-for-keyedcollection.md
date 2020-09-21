---
ms.openlocfilehash: 9cd1d0955b8b77cb77d5c6938b37d9042d8144f6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606855"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="811da-101">Verbesserung der Datenbindung für KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="811da-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="811da-102">Details</span><span class="sxs-lookup"><span data-stu-id="811da-102">Details</span></span>

<span data-ttu-id="811da-103">Korrektur von <xref:System.Windows.Data.Binding>: Falsche Verwendung von IList-Indexer, wenn das Quellobjekt einen benutzerdefinierten Indexer mit derselben Signatur (z. B. KeyedCollection&lt;int,TItem&gt;) deklariert.</span><span class="sxs-lookup"><span data-stu-id="811da-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="811da-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="811da-104">Suggestion</span></span>

<span data-ttu-id="811da-105">Damit eine Anwendung für eine ältere Version von dieser Änderung profitiert, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Zudem muss die Änderung aktiviert werden, indem der folgende [AppContext-Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) zum <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und auf <code>false</code> festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="811da-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="811da-106">name</span><span class="sxs-lookup"><span data-stu-id="811da-106">Name</span></span>    | <span data-ttu-id="811da-107">Wert</span><span class="sxs-lookup"><span data-stu-id="811da-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="811da-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="811da-108">Scope</span></span>   |<span data-ttu-id="811da-109">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="811da-109">Major</span></span>|
|<span data-ttu-id="811da-110">Version</span><span class="sxs-lookup"><span data-stu-id="811da-110">Version</span></span>|<span data-ttu-id="811da-111">4.8</span><span class="sxs-lookup"><span data-stu-id="811da-111">4.8</span></span>|
|<span data-ttu-id="811da-112">Typ</span><span class="sxs-lookup"><span data-stu-id="811da-112">Type</span></span>|<span data-ttu-id="811da-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="811da-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="811da-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="811da-114">Affected APIs</span></span>

<span data-ttu-id="811da-115">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="811da-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
