---
title: Serialisierung von Steuerzeichen mit DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: b6468bc4ae37765d969a1f92b16967cc656ab7ff
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452629"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="6ecbf-102">Entschärfung: Serialisierung von Steuerzeichen mit DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="6ecbf-102">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="6ecbf-103">Ab .NET Framework 4.7 hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8.</span><span class="sxs-lookup"><span data-stu-id="6ecbf-103">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="6ecbf-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="6ecbf-104">Impact</span></span>

<span data-ttu-id="6ecbf-105">Bis .NET Framework 4.6.2 serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den Standards ECMAScript V6 und V8 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="6ecbf-105">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="6ecbf-106">Für Apps mit Zielversionen ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel.</span><span class="sxs-lookup"><span data-stu-id="6ecbf-106">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="6ecbf-107">Dies betrifft die folgenden APIs:</span><span class="sxs-lookup"><span data-stu-id="6ecbf-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a><span data-ttu-id="6ecbf-108">Minderung</span><span class="sxs-lookup"><span data-stu-id="6ecbf-108">Mitigation</span></span>

<span data-ttu-id="6ecbf-109">Für Apps mit Zielversionen ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ecbf-109">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="6ecbf-110">Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6ecbf-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="6ecbf-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ecbf-111">See also</span></span>

- [<span data-ttu-id="6ecbf-112">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="6ecbf-112">Application compatibility</span></span>](application-compatibility.md)
