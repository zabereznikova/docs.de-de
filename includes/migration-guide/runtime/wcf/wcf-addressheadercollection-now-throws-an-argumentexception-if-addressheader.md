---
ms.openlocfilehash: d29be721b50d1c93723b325774a06e86f77dbebf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621222"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="99a4d-101">Der WCF-Konstruktor AddressHeaderCollection löst jetzt eine ArgumentException aus, wenn ein addressHeader-Element den Wert NULL aufweist</span><span class="sxs-lookup"><span data-stu-id="99a4d-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="99a4d-102">Details</span><span class="sxs-lookup"><span data-stu-id="99a4d-102">Details</span></span>

<span data-ttu-id="99a4d-103">Ab .NET Framework 4.7.1 löst der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>-Konstruktor eine <xref:System.ArgumentException> aus, wenn ein Element den Wert <code>null</code> aufweist.</span><span class="sxs-lookup"><span data-stu-id="99a4d-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="99a4d-104">In .NET Framework 4.7 und früheren Versionen wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="99a4d-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="99a4d-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="99a4d-105">Suggestion</span></span>

<span data-ttu-id="99a4d-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="99a4d-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="99a4d-107">name</span><span class="sxs-lookup"><span data-stu-id="99a4d-107">Name</span></span>    | <span data-ttu-id="99a4d-108">Wert</span><span class="sxs-lookup"><span data-stu-id="99a4d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="99a4d-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="99a4d-109">Scope</span></span>   |<span data-ttu-id="99a4d-110">Gering</span><span class="sxs-lookup"><span data-stu-id="99a4d-110">Minor</span></span>|
|<span data-ttu-id="99a4d-111">Version</span><span class="sxs-lookup"><span data-stu-id="99a4d-111">Version</span></span>|<span data-ttu-id="99a4d-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="99a4d-112">4.7.1</span></span>|
|<span data-ttu-id="99a4d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="99a4d-113">Type</span></span>|<span data-ttu-id="99a4d-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="99a4d-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="99a4d-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="99a4d-115">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
