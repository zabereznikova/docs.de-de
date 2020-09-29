---
ms.openlocfilehash: e8b98e465228afd07432e737bb16aefb1b979973
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770836"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="41e59-101">Der WCF-Konstruktor AddressHeaderCollection löst jetzt eine ArgumentException aus, wenn ein addressHeader-Element den Wert NULL aufweist</span><span class="sxs-lookup"><span data-stu-id="41e59-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="41e59-102">Details</span><span class="sxs-lookup"><span data-stu-id="41e59-102">Details</span></span>

<span data-ttu-id="41e59-103">Ab .NET Framework 4.7.1 löst der <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>-Konstruktor eine <xref:System.ArgumentException> aus, wenn ein Element den Wert `null` aufweist.</span><span class="sxs-lookup"><span data-stu-id="41e59-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="41e59-104">In .NET Framework 4.7 und früheren Versionen wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="41e59-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="41e59-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="41e59-105">Suggestion</span></span>

<span data-ttu-id="41e59-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer Datei „App.config“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="41e59-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
