---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606557"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="219cc-101">.NET COM hat die ByRef-SafeArray-Parameter für Ereignisse erfolgreich gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="219cc-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="219cc-102">Details</span><span class="sxs-lookup"><span data-stu-id="219cc-102">Details</span></span>

<span data-ttu-id="219cc-103">In .NET Framework 4.7.2 und früheren Version konnte der ByRef-[SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter für ein COM-Ereignis nicht wieder in nativen Code gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="219cc-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="219cc-104">Durch diese Änderung der [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter wieder erfolgreich gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="219cc-104">With this change the [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="219cc-105">[X] Quirking</span><span class="sxs-lookup"><span data-stu-id="219cc-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="219cc-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="219cc-106">Suggestion</span></span>

<span data-ttu-id="219cc-107">Wenn ein ordnungsgemäßes Marshalling des ByRef-SafeArray-Parameters bei COM-Ereignissen die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfigurationsoption Ihrer Anwendungskonfiguration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="219cc-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="219cc-108">name</span><span class="sxs-lookup"><span data-stu-id="219cc-108">Name</span></span>    | <span data-ttu-id="219cc-109">Wert</span><span class="sxs-lookup"><span data-stu-id="219cc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="219cc-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="219cc-110">Scope</span></span>   |<span data-ttu-id="219cc-111">Gering</span><span class="sxs-lookup"><span data-stu-id="219cc-111">Minor</span></span>|
|<span data-ttu-id="219cc-112">Version</span><span class="sxs-lookup"><span data-stu-id="219cc-112">Version</span></span>|<span data-ttu-id="219cc-113">4.8</span><span class="sxs-lookup"><span data-stu-id="219cc-113">4.8</span></span>|
|<span data-ttu-id="219cc-114">Typ</span><span class="sxs-lookup"><span data-stu-id="219cc-114">Type</span></span>|<span data-ttu-id="219cc-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="219cc-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="219cc-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="219cc-116">Affected APIs</span></span>

<span data-ttu-id="219cc-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="219cc-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
