---
ms.openlocfilehash: 3506653bfc749ae3d8002715ca72ca89de7a681b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025395"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="93edf-101">Der WCF-Konstruktor AddressHeaderCollection löst jetzt eine ArgumentException aus, wenn ein addressHeader-Element den Wert NULL aufweist</span><span class="sxs-lookup"><span data-stu-id="93edf-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="93edf-102">Details</span><span class="sxs-lookup"><span data-stu-id="93edf-102">Details</span></span>

<span data-ttu-id="93edf-103">Ab .NET Framework 4.7.1 löst der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>-Konstruktor eine <xref:System.ArgumentException> aus, wenn ein Element den Wert `null` aufweist.</span><span class="sxs-lookup"><span data-stu-id="93edf-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="93edf-104">In .NET Framework 4.7 und früheren Versionen wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="93edf-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="93edf-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="93edf-105">Suggestion</span></span>

<span data-ttu-id="93edf-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer Datei „App.config“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="93edf-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="93edf-107">name</span><span class="sxs-lookup"><span data-stu-id="93edf-107">Name</span></span>    | <span data-ttu-id="93edf-108">Wert</span><span class="sxs-lookup"><span data-stu-id="93edf-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="93edf-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="93edf-109">Scope</span></span>   | <span data-ttu-id="93edf-110">Gering</span><span class="sxs-lookup"><span data-stu-id="93edf-110">Minor</span></span>   |
| <span data-ttu-id="93edf-111">Version</span><span class="sxs-lookup"><span data-stu-id="93edf-111">Version</span></span> | <span data-ttu-id="93edf-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="93edf-112">4.7.1</span></span>   |
| <span data-ttu-id="93edf-113">Typ</span><span class="sxs-lookup"><span data-stu-id="93edf-113">Type</span></span>    | <span data-ttu-id="93edf-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="93edf-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="93edf-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="93edf-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
