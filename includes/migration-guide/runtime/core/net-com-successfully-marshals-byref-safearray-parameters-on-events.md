---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497862"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="1b7cb-101">.NET COM hat die ByRef-SafeArray-Parameter für Ereignisse erfolgreich gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="1b7cb-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="1b7cb-102">Details</span><span class="sxs-lookup"><span data-stu-id="1b7cb-102">Details</span></span>

<span data-ttu-id="1b7cb-103">In .NET Framework 4.7.2 und früheren Version konnte der ByRef-[SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter für ein COM-Ereignis nicht wieder in nativen Code gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="1b7cb-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="1b7cb-104">Durch diese Änderung der [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)-Parameter wieder erfolgreich gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="1b7cb-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="1b7cb-105">[X] Quirking</span><span class="sxs-lookup"><span data-stu-id="1b7cb-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="1b7cb-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1b7cb-106">Suggestion</span></span>

<span data-ttu-id="1b7cb-107">Wenn ein ordnungsgemäßes Marshalling des ByRef-SafeArray-Parameters bei COM-Ereignissen die Ausführung unterbricht, können Sie diesen Code deaktivieren, indem Sie die folgende Konfigurationsoption Ihrer Anwendungskonfiguration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1b7cb-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1b7cb-108">name</span><span class="sxs-lookup"><span data-stu-id="1b7cb-108">Name</span></span>    | <span data-ttu-id="1b7cb-109">Wert</span><span class="sxs-lookup"><span data-stu-id="1b7cb-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b7cb-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="1b7cb-110">Scope</span></span>   |<span data-ttu-id="1b7cb-111">Gering</span><span class="sxs-lookup"><span data-stu-id="1b7cb-111">Minor</span></span>|
|<span data-ttu-id="1b7cb-112">Version</span><span class="sxs-lookup"><span data-stu-id="1b7cb-112">Version</span></span>|<span data-ttu-id="1b7cb-113">4.8</span><span class="sxs-lookup"><span data-stu-id="1b7cb-113">4.8</span></span>|
|<span data-ttu-id="1b7cb-114">Typ</span><span class="sxs-lookup"><span data-stu-id="1b7cb-114">Type</span></span>|<span data-ttu-id="1b7cb-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1b7cb-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1b7cb-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1b7cb-116">Affected APIs</span></span>

<span data-ttu-id="1b7cb-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="1b7cb-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
